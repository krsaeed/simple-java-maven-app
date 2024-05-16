pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') { 
            steps {
                bat 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
        stage('Deliver') {
            steps {
                bat 'C:/ProgramData/Jenkins/.jenkins/workspace/maven-java-pipe/jenkins/scripts/deliver.bat'
            }
        }
    }
}
