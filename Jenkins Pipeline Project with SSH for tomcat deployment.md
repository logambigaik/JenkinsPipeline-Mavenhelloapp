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
