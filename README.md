# WordpressBackupTool #

Pure backup tool to backup your Wordpress installation out of the box via WebFrontend (PHP)

**Contributors:** number42io, hoenick  
**Tags:** wordpress, backup, backups, zip, files, archive, webfrontend, extract, restore

## Description ##
Goal is to backup and restore Wordpress installation, if you are developing into the source of plugins or theme. So that you have the possibility to roll back to the previous version. This tool should be independent from Wordpress, so that you can run it also if you have an typo in the theme or so. The user are more developer, which developing or adjusting some e.g. in the theme via the integrated Wordpress Theme editor. Sample user having no SSH or FTP, but will change somthing via the Web. This tool gives you always the possibility to rollback - from everywhere.

### Features ###

* Define Wordpress installations to backup (config.php)
* Backup Wordpress with 1-Click
* Restore Wordpress Backup with 1-Click
* Show done backups

### Screenshot ###
Example how-to manage backups for multi WP instalaltion for development and/or testing.
![](https://raw.githubusercontent.com/number42io/wordpressbackuptool/master/img/screenshot1.png)

## Frequently Asked Questions ##

**Can I get support?**

Yes and no. Due to the fact that this is freeware, we will not react in a definied time window, but we will try to support you at your questions a soon as possiblie.

**Where can I give feedback or ask support questions?**

For support questions or feedback please contact us at info@number42.io

## Installation ##

1. Create a folder at your Webserver, where your Wordpress installation is running (e.g. /var/www/wpbackup)
2. Prepare your Webserver, so that this folder can be reached via a other DNS than your WP installation
3. Copy inc/config.php.sample to inc/config.php
4. Make that you have the correct rights for your installation, so that the Webserver get write access (e.g. chown -R www-data:www-data /var/www/wpbackup)
5. Setup the array's for your different installation in inc/config.php
6. Adjust the path of .htaccess AuthUserFile
7. Make also sure that your Wordpress installation has write access for restore.

## Shell scripting for deployment (Installation topic 2-6)

    cd /var/www
    sudo mkdir wpbackup
    sudo chown -R www-data:www-data /var/www/wpbackup
    sudo chown -R www-data:www-data /var/www/wpbackup
    sudo -Hu www-data git clone https://github.com/number42io/wordpressbackuptool.git /var/www/wpbackup
    cd /var/www/wpbackup/inc
    sudo -Hu www-data cp config.php.sample config.php
    sudo -Hu www-data sed -i 's|/usr/verwaltung/web/.htusers|/etc/.htusers|g' /var/www/wpbackup/.htaccess
    sudo -Hu www-data mkdir /var/www/wpbackup/backups

## Release Notes ##

#### Version 0.2 / 2015-07-10
* table layout for backup files
* remove ZIP files per link, if needed
* create backup before restore
* show MD5 checksum
* compare current/previous MD5 checksum
* show differences of ZIP, from MD5 checksum

#### Version 0.1 / 2015-07-10

* first development
* create backup ZIP
* restore backup ZIP
* config file

