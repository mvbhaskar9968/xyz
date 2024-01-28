pipeline{

    agent any 

    stages{
        stage('Continouse Download'){
        steps{
            git  branch: 'main', url: 'https://github.com/Cabstux/DEVOPS_Project1.git'
        }
        }
        stage('Print Path') {
    steps {
        sh 'echo $PATH'
    }
}

    }
}