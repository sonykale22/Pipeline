pipeline {
    agent any

    stages {
        
        stage('SCM checkout') {
            steps {
                git branch: 'Master', url: 'https://github.com/sonykale22/Pipeline.git'
                 sh 'mvn compile'

            }
        }
    }
}
