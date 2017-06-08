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
rpm -Uvh http://dev.mysql.com/get/mysql57-community-release-el6-7.noarch.rpm
yum repolist enabled | grep "mysql.*-community.*"
yum install mysql-community-server
</pre>
