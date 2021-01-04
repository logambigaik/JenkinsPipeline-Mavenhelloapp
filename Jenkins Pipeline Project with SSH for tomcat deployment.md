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

