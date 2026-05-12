//to check jenkins//
sudo system ctl status jenkins
//to install//
sudo wget -o /etc/apt/keyrings/jenkins-keyring.asc \ https://pkg.jenkins.io/debian-stable/jenkins-io-2026.key

echo "deb[signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \ https://pkg.jenkins.io/debian-stable binary/ \ sudotee\ /etc/apt/sources.list.d/jenkins.list> /dev/null

sudo apt update

sudo apt install jenkins
// then to login open//
http:/localhost:8080
// to get password//
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
//copy paste the password//


for 6th program
//create maven project
//then run it 'mvn package'
//after running type this in terminal//

git config --global user.email "poorvikapoorvi1230@gmail.com"
git config --global user.name "poorvikapoorvi1230-blip"

//to get ssh key//
ssh-keygen -t ed25519 -C "poorvikapoorvi1230@gmail.com"
cat ~/.ssh/id_ed25519.pub
//after creating in terminal//
ssh -T git@github.com

//then can copy paste commd from git hub or typr this//
git init
git add pom.xml
git add src
git commit -m "first commit"
git brach -m main
git remove set -url origin git@github.com:poorvikapoorvi1230-blip/devops.git
git push -u origin main

//then jenkins pipeline code//

pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: '(//our url//)'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
