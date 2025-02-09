pipeline {
    agent any

    stages {
        
        stage('SCM checkout') {
            steps {
                git 'https://github.com/sonykale22/maven-project-9181.git'
              

            }
        }
        stage('package') 
        {
            steps {
              withMaven(globalMavenSettingsConfig: '', jdk: 'Java_home', maven: 'MVN_Home', mavenSettingsConfig: '', traceability: true) {
              sh 'mvn clean package'

            }
        }
    }
}
}