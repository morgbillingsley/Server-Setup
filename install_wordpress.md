# Install WordPress

### Navigate to Apache root directory

```shell
cd /var/www/html
```

### Download WordPress zip file

```shell
wget https://wordpress.org/latest.tar.gz
```

### Unzip the package

```shell
tar -xzvf latest.tar.gz
```

- Delete the downloaded zip file

```shell
rm -R latesr.tar.gz
```

### Move all files into apache root directory

```shell
mv -v ~/../var/www/html/wordpress/* ~/../var/www/html/
```

### Delete the empty WordPress directory

```shell
rm -R wordpress
```

### Change Permissions

- index.php

```shell
chmod -v 666 index.php
```

- .htaccess

```shell
touch .htaccess
```

```shell
chmod -v 666 .htaccess
```

- uploads

```shell
cd /var/www/html/wp-content
```

```
mkdir uploads
```

- Give php permission to write to uploads folder

```shell
chown -R www-data /var/www/html/wp-content/uploads
```

### Restart Apache

```shell
service apache2 restart
```

### Run mod_rewrite

```shell
a2enmod rewrite
```

- restart apache

```shell
service apache2 restart
```

- adjust virtual host configuration

```shell
nano /etc/apache2/sites-available/000-default.conf
```

- Enter the following below `Document Root /var/www/html`

```html
<Directory /var/www/html>
   Options Indexes FollowSymLinks MultiViews
   AllowOverride All
   Order allow,deny
   allow from all
</Directory>
```

- Write Out `Ctrl + w`

- Exit `Ctrl + x`

- Restart Apache

```shell
service apache2 restart
```