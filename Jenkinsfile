pipeline{
    agent any
    stages{
        stage('Checkout the code'){
            steps{
                git branch: 'main', url: 'https://github.com/srinivasarao-ceq/Simple-Maven_project.git'
            }
        }
        stage('Build the project with Maven'){
            steps{
                sh 'mvn clean packages'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
    }

}
