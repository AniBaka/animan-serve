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
Enter password for user root: Enter New Root Password
VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?
Press y|Y for Yes, any other key for No: y
There are three levels of password validation policy:
LOW    Length >= 8
MEDIUM Length >= 8, numeric, mixed case, and special characters
STRONG Length >= 8, numeric, mixed case, special characters and dictionary                  file
Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 2
Using existing password for root.
Estimated strength of the password: 50 
Change the password for root ? ((Press y|Y for Yes, any other key for No) : y
New password: Set New MySQL Password
Re-enter new password: Re-enter New MySQL Password
Estimated strength of the password: 100 
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : y
By default, a MySQL installation has an anonymous user,
allowing anyone to log into MySQL without having to have
a user account created for them. This is intended only for
testing, and to make the installation go a bit smoother.
You should remove them before moving into a production
environment.
Remove anonymous users? (Press y|Y for Yes, any other key for No) : y
Success.
Normally, root should only be allowed to connect from
'localhost'. This ensures that someone cannot guess at
the root password from the network.
Disallow root login remotely? (Press y|Y for Yes, any other key for No) : y
Success.
By default, MySQL comes with a database named 'test' that
anyone can access. This is also intended only for testing,
and should be removed before moving into a production
environment.
Remove test database and access to it? (Press y|Y for Yes, any other key for No) : y
- Dropping test database...
Success.
- Removing privileges on test database...
Success.
Reloading the privilege tables will ensure that all changes
made so far will take effect immediately.
Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
Success.
All done! 
</pre>
