pipeline{

    agent any 

    stages{
        stage('Continouse Download'){
        steps{
            git  branch: 'main', url: 'https://github.com/Cabstux/DEVOPS_Project1.git'
        }
        }
        stage('Integration Testion'){
            steps{
                sh'mvn test'
        }
        }
    }
}