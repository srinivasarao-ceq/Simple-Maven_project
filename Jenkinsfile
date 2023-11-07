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
                sh 'mvn clean package'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Deploy into TOmcat server'){
            steps{
                deploy adapters: [tomcat10(credentialsId: 'tomcat_credentials', path: '', url: 'http://54.254.147.204:8090/')], contextPath: 'hello', war: '**/*.war'
            }
        }
    }

}
