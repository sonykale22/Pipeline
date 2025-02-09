pipeline {
    agent any

    stages {
        
        stage('SCM checkout') {
            steps {
                git branch: 'Master', url: 'https://github.com/sonykale22/Pipeline.git'
              

            }
        }
        stage('clean') 
        {
            steps {
              withMaven(globalMavenSettingsConfig: '', jdk: 'Java_home', maven: 'MVN_Home', mavenSettingsConfig: '', traceability: true) {
              sh 'mvn clean package'

            }
        }
    }
}
}
