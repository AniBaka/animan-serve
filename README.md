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
yum install php71w-common php71w-mbstring php71w-mcrypt php71w-mysqlnd php71w-gd -y
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
</pre>
