pipeline {
    agent any
    stages{
        stage(' clean and compile '){
            steps{
            echo "this is bugfix branch!"
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
