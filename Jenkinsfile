pipeline {
    agent any

    stages {
        stage('Git Download') {
            steps {
                git  branch: 'main', url: 'https://github.com/mvbhaskar9968/xyz.git'
            }
        }
        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Integration Test') {
            steps {
                sh 'mvn verify -DskipUnitTests'
            }
        }
        
        stage('Maven Build') {
            steps {
                sh 'mvn clean install'
            }
        }
      stage('Deploy') {
            steps {
               script {
          deploy adapters: [tomcat9(tomcat: 'tomcat', path: '', url: 'http://54.87.103.17:8080/')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' 
                      }
                  }
      }
    }
}
