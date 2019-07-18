# Add browscap Function

- ## Check to see if the browscap.ini or php_browscap.ini file currently exists in your file system

```shell
cd /etc/php/(PHP_VERSION)/mods-available/
```

```shell
ls -a
```
- ## If browscap exists, move to the next step. If it does not, carry on to the substeps

  - Download browscap for php

```shell
wget http://browscap.org/stream?q=PHP_BrowsCapINI
```
  - Rename the downloaded file

```shell
mv stream\?q\=PHP_BrowsCapINI php_browscap.ini
```
- ## Add browscap to php.ini

```shell
nano /etc/php/(PHP_VERSION)/apache2/php.ini
```
  - Search for `browscap` using `Ctrl + w`
    - Remove the `;` before the `browscap =` text
    - After the `browscap =` insert the following

```shell
/etc/php/(PHP_VERSION)/mods-available/php_browscap.ini
```
- ## Restart Apache

```shell
service apache2 restart
```