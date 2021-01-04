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

Next,

![Capture](https://user-images.githubusercontent.com/54719289/103564654-ea93d900-4ee4-11eb-8e66-1ef4889b7644.JPG)

Next,

![Capture](https://user-images.githubusercontent.com/54719289/103564734-0eefb580-4ee5-11eb-8efe-e53d09e7c7ea.JPG)

Next,

![Capture](https://user-images.githubusercontent.com/54719289/103564841-3f375400-4ee5-11eb-9e4d-abf82d242ed6.JPG)

Next,

![Capture](https://user-images.githubusercontent.com/54719289/103564910-5d9d4f80-4ee5-11eb-9047-830d3c40876d.JPG)

Next,

![Capture](https://user-images.githubusercontent.com/54719289/103565003-84f41c80-4ee5-11eb-9fea-46b6083762ca.JPG)

Next,

![Capture](https://user-images.githubusercontent.com/54719289/103565063-a8b76280-4ee5-11eb-9fb2-5f1dee76dcb7.JPG)

Next,

![Capture](https://user-images.githubusercontent.com/54719289/103565155-d3092000-4ee5-11eb-9e10-3033f0f6afc1.JPG)

git clone https://github.com/logambigaik/Maven-webapp.git

![Capture](https://user-images.githubusercontent.com/54719289/103566407-fb921980-4ee7-11eb-8654-f963d0de46b5.JPG)


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


No Maven-webapp file in Tomcat,


![Capture](https://user-images.githubusercontent.com/54719289/103566601-41e77880-4ee8-11eb-8a55-96bf1a8dc5c2.JPG)


Using ssh-keygen copying file from Jenkins to Tomcat:
====================================================

in Jenkins server,
ssh-keygen

![Capture](https://user-images.githubusercontent.com/54719289/103566823-b6bab280-4ee8-11eb-920e-96b8f0e21d15.JPG)

![Capture](https://user-images.githubusercontent.com/54719289/103566990-fbdee480-4ee8-11eb-9cee-890a9e529474.JPG)

id_rsa-private key
id_rsa.pub -public key

Copy the public key from jenkins and place it in tomcat -authorized_keys.

![Capture](https://user-images.githubusercontent.com/54719289/103567191-58da9a80-4ee9-11eb-8ad0-d70ae289c6c0.JPG)


in Tomcat Server:
================

ssh-keygen,

![Capture](https://user-images.githubusercontent.com/54719289/103567689-44e36880-4eea-11eb-9eb2-b7ccdc3fa2b3.JPG)


After pasting the jenkins id_rsa.pub in authorized_keys (tomcat),

![Capture](https://user-images.githubusercontent.com/54719289/103567908-9f7cc480-4eea-11eb-9733-d4b8c6a0c3ff.JPG)


in Jenkins:
==========

ssh root@172.31.30.146

![Capture](https://user-images.githubusercontent.com/54719289/103568201-2c278280-4eeb-11eb-86a1-096ee78fcf64.JPG)

Now login to tomcat from jenkins,

Logout from tomcat server and copy the location of war file:

in Tomcat Server:
===============

use scp command to copy the jenkin's war file

scp <source-path> user@ipaddr:<destinationpath>
scp /root/Maven-webapp/target/Maven-webapp.war root@172.31.30.146:/opt/apache-tomcat-8.5.61/webapps
  
![Capture](https://user-images.githubusercontent.com/54719289/103568829-44e46800-4eec-11eb-9571-2676345949f4.JPG)

in Jenkins server:
================

For permission denied issue, change the PasswordAuthentication no to yes(/etc/ssh/sshd_config in jenkins)

Before update,

![Capture](https://user-images.githubusercontent.com/54719289/103569043-9ee52d80-4eec-11eb-9af2-fbb4346e3d30.JPG)

After update,

![Capture](https://user-images.githubusercontent.com/54719289/103569143-ccca7200-4eec-11eb-8dbb-8cda285e6641.JPG)

After issuing SCP command in Jenkins:
====================================

![Capture](https://user-images.githubusercontent.com/54719289/103569675-bbce3080-4eed-11eb-86f0-38870a3bc198.JPG)

Tomcat server:
=============

![Capture](https://user-images.githubusercontent.com/54719289/103569778-f0da8300-4eed-11eb-87a2-e22237915331.JPG)

Tomcat UI:

![Capture](https://user-images.githubusercontent.com/54719289/103569778-f0da8300-4eed-11eb-87a2-e22237915331.JPG)
  





