pipeline {
    agent any
    stages{
        stage(' clean and compile '){
            steps{
            echo "HELLO WORLD!"
            echo "HELLO JENKINS"
            echo "DONTIREDDY VENKATA KRISHNA REDDY"
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
