Jenkins Pipeline for Tomcat Deploy:
==================================

![Capture](https://user-images.githubusercontent.com/54719289/103571270-97278800-4ef0-11eb-8fa6-774f7dd8508b.JPG)


Pipeline Code:

![Capture](https://user-images.githubusercontent.com/54719289/103571473-f1c0e400-4ef0-11eb-85de-03994c0d8fdf.JPG)


Pipeline Syntax for script:

![Capture](https://user-images.githubusercontent.com/54719289/103571607-3482bc00-4ef1-11eb-9ff1-a1f10954fe69.JPG)

Pipeline Code:

pipeline{
    agent any
    stages{
        stage('SCM'){
            steps{
                git branch: 'main', url: 'https://github.com/logambigaik/Maven-webapp.git'
            }
        }
        stage('Build Artifact'){
            steps{
                sh 'mvn clean install'
            }
        }
        
        stage('Deploy to Tomcat'){
            steps{
                dir('target') {
                       sh 'scp target/Maven-webapp.war root@172.31.30.146:/opt/apache-tomcat-8.5.61/webapps'
                       
                }        
            }
        }
        
    }
}


![Capture](https://user-images.githubusercontent.com/54719289/103572669-f38ba700-4ef2-11eb-817f-d90ff039a527.JPG)


Failed with Hostkey connection :

![Capture](https://user-images.githubusercontent.com/54719289/103573139-c2f83d00-4ef3-11eb-9f86-3866fc29751a.JPG)

SInce we have login with root , need to be login with jenkins user,

Login as jenkin user in Jenkins Sever:
=====================================

su -s /bin/bash jenkins

before that allow permission to jenkin user for visudo ,

![Capture](https://user-images.githubusercontent.com/54719289/103573485-55004580-4ef4-11eb-9438-cf9992964e6b.JPG)

ssh -keys are stored in /var/lib/jenkins/.ssh/id_rsa.pub instead root ->/.ssh/

Copy the id_rsa.pub and place it in tomcat authorized_keys ,

In Jenkins:
=========

![Capture](https://user-images.githubusercontent.com/54719289/103573901-0acb9400-4ef5-11eb-9fca-4b4c9daecd0e.JPG)

In Tomcat:
=========

![Capture](https://user-images.githubusercontent.com/54719289/103574044-3e0e2300-4ef5-11eb-96a6-609898b78127.JPG)

![Capture](https://user-images.githubusercontent.com/54719289/103574512-1a97a800-4ef6-11eb-984c-d7b5957b063f.JPG)

using exit command come out of jenkins user and update visudo (command :sudo visudo ->jenkins ALL=(ALL)       NOPASSWD: ALL)

![Capture](https://user-images.githubusercontent.com/54719289/103574822-a1e51b80-4ef6-11eb-871a-a070804409dd.JPG)

Also enable passwordauthentication as yes in (etc/ssh/sshd_config)


![Capture](https://user-images.githubusercontent.com/54719289/103577368-aca1af80-4efa-11eb-931b-40b6eeea355c.JPG)


![Capture](https://user-images.githubusercontent.com/54719289/103577604-246fda00-4efb-11eb-881a-369e9d24f9e4.JPG)


 


