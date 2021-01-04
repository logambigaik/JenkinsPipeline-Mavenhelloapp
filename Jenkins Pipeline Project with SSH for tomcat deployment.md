Jenkins install  :
===============

wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo
sudo rpm --import http://pkg.jenkins.io/redhat-stable/jenkins.io.key
yum install jenkins -y
sudo service jenkins start

yum install git maven java-1.8* -y

to change hostname :
sudo hostnamectl set-hostname jenkin
sudo -i

![Capture](https://user-images.githubusercontent.com/54719289/103563586-05654e00-4ee3-11eb-8df5-8d0a4d8919e9.JPG)

![Capture](https://user-images.githubusercontent.com/54719289/103564654-ea93d900-4ee4-11eb-8e66-1ef4889b7644.JPG)

![Capture](https://user-images.githubusercontent.com/54719289/103564734-0eefb580-4ee5-11eb-8efe-e53d09e7c7ea.JPG)

Tomcat install:
=============
yum install git maven java-1.8* -y  
in /opt -(third party tools should be installed under /opt folder)
wget https://downloads.apache.org/tomcat/tomcat-8/v8.5.61/bin/apache-tomcat-8.5.61.tar.gz
tar -xvzf apache-tomcat-8.5.60.tar.gz
cd apache-tomcat-8.5.60
cd bin
sh startup.sh

![Capture](https://user-images.githubusercontent.com/54719289/103564486-9983e500-4ee4-11eb-8cdd-1ede87e558cf.JPG)
