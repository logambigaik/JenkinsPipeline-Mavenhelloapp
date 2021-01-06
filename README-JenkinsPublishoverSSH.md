Jenkins install :

wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo

sudo rpm --import http://pkg.jenkins.io/redhat-stable/jenkins.io.key

yum install jenkins -y

yum install git maven java-1.8* -y

sudo service jenkins start

To change hostname :
sudo hostnamectl set-hostname jenkin
git clone https://github.com/logambigaik/Maven-webapp.git -renamed as JenkinsPipeline-Mavenhelloapp



Tomcat install:
yum install git maven java-1.8* -y

in /opt -(third party tools should be installed under /opt folder)

wget https://downloads.apache.org/tomcat/tomcat-8/v8.5.61/bin/apache-tomcat-8.5.61.tar.gz

tar -xvzf apache-tomcat-8.5.60.tar.gz

cd apache-tomcat-8.5.60

cd bin

sh startup.sh

![Capture](https://user-images.githubusercontent.com/54719289/103695442-93fccc80-4fc2-11eb-9849-fa15a0e42325.JPG)




In Jenkin:

ManageJenkin-Manage Plugin-Select Publish over ssh in Available and Choose install without restart option


![Capture](https://user-images.githubusercontent.com/54719289/103695534-c7d7f200-4fc2-11eb-8b17-d3bc75de92ea.JPG)


![Capture](https://user-images.githubusercontent.com/54719289/103695704-1ab1a980-4fc3-11eb-9093-8f78497cd3ec.JPG)

Create new project ->New item ->Enter project name and select pipeline project
==============================================================================


![Capture](https://user-images.githubusercontent.com/54719289/103695822-49c81b00-4fc3-11eb-9dfd-2ce210c66536.JPG)

In tomcat server:
===============

update password authentication as yes in /etc/ssh/sshd_config and restart the service(service sshd restart)

![Capture](https://user-images.githubusercontent.com/54719289/103696560-92340880-4fc4-11eb-9c99-c6898863359a.JPG)


In Jenkins server:
=================

Configure the Publish over the SSH plugin(Manage Jenkins->Configur system)

![Capture](https://user-images.githubusercontent.com/54719289/103696794-fa82ea00-4fc4-11eb-914d-d8054f783b7a.JPG)

![Capture](https://user-images.githubusercontent.com/54719289/103696904-24d4a780-4fc5-11eb-9e13-621dee58455b.JPG)

Note: tomcat root password is important(set password with :passwd root), enter tomcat ipaddress ,nit require to use ssh-keygen in tomcat and jenkins
Also remote directory is mandatory to specify in configure system.

![Capture](https://user-images.githubusercontent.com/54719289/103812075-f4077780-5083-11eb-8f18-4ce6c375e84d.JPG)



Pipeline syntax section sshPublish:
==================================

![Capture](https://user-images.githubusercontent.com/54719289/103811767-6e83c780-5083-11eb-963b-3841351b1bc0.JPG)



![Capture](https://user-images.githubusercontent.com/54719289/103812208-2c0eba80-5084-11eb-9aa0-977fb33c18c7.JPG)


Tomcat server:
=============

![Capture](https://user-images.githubusercontent.com/54719289/103812291-519bc400-5084-11eb-8e9d-57139a580e1a.JPG)



![Capture](https://user-images.githubusercontent.com/54719289/103811767-6e83c780-5083-11eb-963b-3841351b1bc0.JPG)





