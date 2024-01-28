pipeline{

    agent any 

    stages{
        stage('continouse Download'){
        steps{
            git  branch: 'main', url: 'https://github.com/Cabstux/DEVOPS_Project1.git'
        }
        }
        stage('Integration testing'){
            steps{
                sh 'mvn test'
        }
        }
    }
}