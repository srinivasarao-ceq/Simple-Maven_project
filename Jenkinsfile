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
            //    sshagent(['tomcat-server_credentials']) {
            //     sh 'scp target/*.jar ec2-user@http://54.254.147.204:/home/ec2-user/apache-tomcat-9.0.82/webapps/'
            //    }
                 deploy adapters: [tomcat9(credentialsId: 'tomcat_ui', path: '', url: 'http://54.254.147.204:8090/')], contextPath: 'hello', war: '**/*.jar'
            }
        }
    }

}
