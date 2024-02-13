pipeline {
    agent any
    stages{
        stage(' clean and compile '){
            steps{
            echo "hello world!"
            echo "hello jenkins"
            echo "Dontireddy Venkata Krishna Reddy"
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
