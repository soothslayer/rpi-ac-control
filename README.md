rpi-ac-control
==============

Control your AC w/ a Raspberry Pi &amp; USB Infrared Toy v2 (TMP102 temp sensor and rPi camera are optional) w/ PHP

Here are the commands I ran on my raspberry pi to get this up and running as root:
apt-get update
apt-get upgrade
apt-get install mysql-client mysql-server php-pear php5-dev mercurial i2c-tools
pecl install dio channel://pecl.php.net/dio-0.0.6
echo "extension=dio.so" >> /etc/php5/cli/php.ini
echo "extension=dio.so" >> /etc/php5/apache2/php.ini
hg clone https://bitbucket.org/cdrum/phpirtoy
vim /etc/modprobe.d/raspi-blacklist.conf
#comment out blacklist i2c-bcm2708
#add modprobe i2c-dev to crontab
#or add i2c-dev to /etc/modules
