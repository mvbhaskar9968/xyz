pipeline {
    agent any

    stages {
        stage('Continouse Download') {
            steps {
                git  branch: 'main', url: 'https://github.com/Cabstux/DEVOPS_Project1.git'
            }
        }
        stage('Integration Testion') {
            steps {
                sh '/usr/local/bin/mvn verify -DskipUnitTests'
            }
        }
        stage('Unit Testing') {
            steps {
                sh '/usr/local/bin/mvn test'
            }
        }
    }
}
