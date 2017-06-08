# animan-serve
This manual configuring AniBaka Team Server

# Install packages on CentOS 6
<pre>yum update -y
yum install nano mc vim wget -y
rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm
rpm -Uvh https://mirror.webtatic.com/yum/el6/latest.rpm
yum install nginx php71w httpd -y
yum install htop iptraf tcpdump -y
yum install iftop -y
yum install php71w-common php71w-fpm php71w-cli php71w-mbstring php71w-mcrypt php71w-mysqlnd php71w-gd -y
rpm -Uvh http://dev.mysql.com/get/mysql57-community-release-el6-7.noarch.rpm
yum repolist enabled | grep "mysql.*-community.*"
yum install mysql-community-server
</pre>

# Check installed software
<pre>
[root@localhost ~]# mysql -V
mysql  Ver 14.14 Distrib 5.7.18, for Linux (x86_64) using  EditLine wrapper

[root@localhost ~]# nginx -v
nginx version: nginx/1.10.2

[root@localhost ~]# httpd -v
Server version: Apache/2.2.15 (Unix)
Server built:   Mar 22 2017 06:52:55

[root@localhost /]# php -v
PHP 7.1.5 (cli) (built: May 12 2017 22:14:00) ( NTS )
Copyright (c) 1997-2017 The PHP Group
Zend Engine v3.1.0, Copyright (c) 1998-2017 Zend Technologies
</pre>

# Setup root password on MySQL
<pre>
[root@localhost /]# grep 'temporary password' /var/log/mysqld.log
2017-06-08T15:58:30.143866Z 1 [Note] A temporary password is generated for root@localhost: QHn?lDo#U5)J

[root@localhost /]# mysql_secure_installation

Securing the MySQL server deployment.

Enter password for user root:
</pre>
