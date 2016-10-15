Install Fedora 23

sudo su -
rpm -Uvh http://f23.amahi.org/noarch/hda-release-6.9.0-1.noarch.rpm
hda-install pnk4ynt       <INSTALL-CODE>

fix for mysql
echo "update servers set name='mysql' where comment='MariaDB Server'" | mysql -uroot -phda hda_production
