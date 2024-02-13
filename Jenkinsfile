pipeline {
    agent any
    stages{
        stage(' clean and compile '){
            steps{
            sh "hello world!"
            sh "mvn clean compile"
            }
        }
        stage('test'){
            steps{
            sh "mvn test "
            }
        }
        stage('package'){
            steps{
            sh "mvn package "
            }
        }
    }
}
