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
                sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@43.204.149.125:/usr/share/tomcat/webapps'
}
                }
            }
        }
    }
