pipeline {
    agent any

    stages {
        
        stage('SCM checkout') {
            steps {
                git 'https://github.com/sonykale22/maven-project-9181.git'
            }
        }

        stage('Validate') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'Java_home', maven: 'MVN_Home', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn validate'
                }
            }
        }

        stage('Compile') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'Java_home', maven: 'MVN_Home', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn compile'
                }
            }
        }

        stage('Package the code') {
            steps {
                withMaven(globalMavenSettingsConfig: '', jdk: 'Java_home', maven: 'MVN_Home', mavenSettingsConfig: '', traceability: true) {
                    sh 'mvn clean package'
                }
            }
        }
        stage('Deploy the code') {
            steps {
                sshagent(['DevCICD']) {
                ssh -o StrictHostKeyChecking=no ec2-user@172.31.50.166 "sudo -u tomcat mv /tmp/webapp.war /usr/share/tomcat/webapps/"
}
                }
            }
        }
    }
