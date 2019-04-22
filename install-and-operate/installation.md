---
description: >-
  These instructions are for installing PM415, MySQL, and Elastic Search on a
  single instance.
---

# Ubuntu 18.04

## Requirements

* Ubuntu 18.04 or higher
* A SendGrid account for invitation links, password resets, and comments
* Firewall rules to open ports 80, 443 and 9200
* Root access

## Install Node.js

```text
curl -sL https://deb.nodesource.com/setup_10.x | sudo bash -
sudo apt-get install nodejs
sudo apt-get install build-essential
```

## Install PM415

```text
git clone https://github.com/mreider/pm415
cd pm415
sudo npm install
sudo npm install uuid --s
```

## Install MySQL \(MariaDB\)

Answer 'Y' to the secure installation prompts.

```text
sudo apt install software-properties-common
sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
sudo add-apt-repository 'deb [arch=amd64] http://mirrors.supportex.net/mariadb/repo/10.2/ubuntu bionic main'
sudo apt -y install mariadb-server mariadb-client
sudo mysql_secure_installation
mysql -u root -p
CREATE DATABASE IF NOT EXISTS zagnut;
exit
```

## Install Elastic Search

```text
sudo add-apt-repository -y ppa:webupd8team/java
sudo apt update
sudo apt install default-jdk
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/6.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-6.x.list
sudo apt update && sudo apt-get install elasticsearch
sudo systemctl daemon-reload 
sudo systemctl enable elasticsearch.service 
```

Edit the file `/etc/elasticsearch/elasticsearch.yml` and add the following

```text
network.host: 127.0.0.1
```

Start the service and check its status

```text
sudo systemctl start elasticsearch.service
sudo systemctl status elasticsearch.service
```

If you see an error like `'Cannot allocate memory'` you must be running a small instance.  Lower the JVM heap size by editing the file `/etc/elasticsearch/jvm.options` by changing the values `xms1g` to `xms100m` and `xmx1g` to `xmx100m`. 

If you changed your heap size - restart the service as follows:

```text
sudo systemctl restart elasticsearch.service
```

## Install Caddy Server to support SSL

[Caddy](https://caddyserver.com/features) is HTTP server that supports automatic SSL through [LetsEncrypt](https://letsencrypt.org/). The following installs the personal version of Caddy.

```text
curl https://getcaddy.com | bash -s personal
```

Give caddy the ability to bind to privileged ports as a non-root user:

```text
sudo setcap 'cap_net_bind_service=+ep' /usr/local/bin/caddy
```

Set up needed user, group, and directories

```text
sudo groupadd -g 33 www-data
sudo useradd \
  -g www-data --no-user-group \
  --home-dir /var/www --no-create-home \
  --shell /usr/sbin/nologin \
  --system --uid 33 www-data

sudo mkdir /etc/caddy
sudo chown -R root:root /etc/caddy
sudo mkdir /etc/ssl/caddy
sudo chown -R root:www-data /etc/ssl/caddy
sudo chmod 0770 /etc/ssl/caddy
```

Create Caddy Systemd service unit

```text
wget https://raw.githubusercontent.com/mholt/caddy/master/dist/init/linux-systemd/caddy.service
sudo cp caddy.service /etc/systemd/system/
sudo chown root:root /etc/systemd/system/caddy.service
sudo chmod 644 /etc/systemd/system/caddy.service
sudo systemctl daemon-reload
```

Edit the file `/etc/caddy/Caddyfile` as follows:

```text
your-site.com {
        tls email@email.com
        gzip
        proxy / localhost:3000 {
                transparent
                websocket
        }
}
```

Start the caddy service

```text
sudo systemctl start caddy.service
```

## Create environment variables

Edit the file `/etc/environment` and add the following environment variables

```text
NODE_ENV=PRODUCTION
KEEP_PROCESS_AWAKE=1
DATABASE_URL=mysql://root:password@localhost:3306
SENDGRID_USERNAME=foo
SENDGRID_PASSWORD=bar
DOMAIN_URL=pm415.com
ELASTIC_SEARCH_URL=http://localhost:9200
FEEDLIST=http://www.mindtheproduct.com/feed/,https://www.reddit.com/r/prodmgmt/.rss?format=xml
WHITELIST=/localhost/,/pm415.com/
APPKEY=097129fcba4ab7002604f7c27503fcf4b46c18708f2852cb654dc
SITEURL_DEV=http://localhost
SITE_PORT=8080
```

Load  environment variables into your session

```text
source /etc/environment
```

## Run database migrations

```text
cd pm415
sudo npm i -g knex
sudo knex migrate:latest
sudo knex seed:run
```

## Configure the app

Edit `~/pm415/config.js` to change the appkey and add your domain to the whitelist and siteURL

```text
...

siteUrl: 'http://localhost:3000/',
appKey: 'create-a-new-appkey-here-random-numbers-etc',

...

const whitelist = [
        /localhost/,
        /zagnut.herokuapp.com/,
        /pm415.com/,
        /yourdomain.com/
      ];

...

if (process.env.NODE_ENV === 'production') {
  config.siteUrl = 'http://your-url.com/';
}

...
```

## Install and start pm2

```text
sudo npm install pm2@latest -g
pm2 start server.js --name pm415
```

