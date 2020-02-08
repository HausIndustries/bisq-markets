# Bisq Markets Website+API
A simple web interface to view Bisq markets.

This is a bare-bones implementation that reads the JSON files created by Bisq
and publishes an API for web clients to access them.

# Performance, or lack thereof.

At present, no database is used and backend operations are very inefficient.

This is OK for the moment as there is little Bisq data, but the implementation
will need to be optimized when Bisq volume picks up.

I have separated the data access classes such that it should be simple to plugin
more efficient strategies.

# Requirements

* Ubuntu 18.04 LTS

# Installation

First, [setup your Bisq Seednode](https://github.com/bisq-network/bisq/tree/master/seednode#bisq-seed-node) so you have Bisq running and fully synced. Then, run the intallation script from this repo to install Bisq Markets API into the Apache webroot.

```bash
curl -s https://raw.githubusercontent.com/bisq-network/bisq-markets/master/install_bisq_markets_debian.sh | sudo bash
```
Navigate in your browser to your webserver docroot.

# Let's Encrypt

You'll need to open ports 80 and 443 on your firewall for HTTP and HTTPS
```bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```

Request an SSL certificate for your server's hostname using certbot
```bash
sudo apt-get install -y python-certbot-apache
sudo certbot --apache -d markets.example.com
```

# API

For now, just check out the API subdirectory.  docs are todo.
