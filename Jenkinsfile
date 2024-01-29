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
        stage('Continouse Build') {
            steps {
                sh '/usr/local/bin/mvn clean install'
            }
        }
        stage('Static Test Analysis') {
            steps {
                script {
                    //Active static test
                    /* groovylint-disable-next-line NestedBlockDepth */
                    withSonarQubeEnv(credentialsId: 'token-sonarqube') {
                        sh '/usr/local/bin/mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
}
