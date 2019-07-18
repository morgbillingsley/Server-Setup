# Install Certbot

### Run super user

```shell
sudo su
```

### Navigate to Apache root directory

```shell
cd /var/www/html
```

### Install Certbot
```shell
apt-get install certbot python-certbot-apache -t stretch-backports
```

### Get and install ssl certificates
```shell
certbot --apache
```

1. Enter a valid email address.
2. Agree to the terms.
3. Do not agree to send your email to the Electronic Frontier Foundation.
4. Enter both `[DOMAIN_NAME]` and `www.[DOMAIN_NAME]` separated by a space or comma.
5. Select the `000-default-le-ssl.conf` option (usually option number 2).
6. Choose the `2. Redirect - Make all requests redirect to secure HTTPS` option

### Restart Apache

```shell
service apache2 restart
```