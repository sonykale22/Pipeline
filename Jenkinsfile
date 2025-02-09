pipeline {
    agent any

    stages {
        
        stage('SCM checkout') {
            steps {
                git 'https://github.com/sonykale22/Pipeline.git'
              

            }
        }
        stage('Hello') 
        {
            steps {
              withMaven(globalMavenSettingsConfig: '', jdk: 'Java_home', maven: 'MVN_Home', mavenSettingsConfig: '', traceability: true) {
              sh 'mvn clean package'

              }
        }
    }
    }
}