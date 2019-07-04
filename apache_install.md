# Apache Installation

### Run sudo

```shell
sudo su
```

### Update

```shell
apt-get update
```

### Install Apache 2, php, and libapache2

```shell
apt-get install apache2 php libapache2-mod-php
```

### Test apache by visiting the ip address of your server

```basic
http://[SERVER_IP_ADDRESS]
```

### Install the MySQL server, MySQL, and php-pear

```shell
apt-get install mysql-server php(PHP_VERSION)-mysql php-pear
```

- Configure MySQL

  - ```shell
mysql_secure_installation
  ```

- Select apache2
  - Select yes to dbconfig-common
  - Enter a password fo MySQL and phpmyadmin

### Restart Apache

```shell
service apache2 restart
```

### Configure Apache for phpmyadmin

1. Edit apache2.conf file

  - ```shell
edit /etc/apache2/apache2.conf
   ```

2. At the end of the file insert the following text

  - ```
Include /etc/phpmyadmin/apache.conf
   ```

### Restart Apache

```shell
service apache2 restart
```

### Install phpmyadmin

```shell
apt-get install phpmyadmin
```

- Check if phpmyadmin page is working in the browser

  - ```
http://[SERVER_IP_ADDRESS]/phpmyadmin
  ```