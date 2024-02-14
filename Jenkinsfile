pipeline {
    agent any
    stages{
        stage(' clean and compile '){
            steps{
            echo "This is master branch"
            sh "mvn clean compile"
            }
        }
        stage('test'){
            steps{
            sh "mvn test "
            }
            post{
                always{
                    junit allowEmptyResults: true, testResults: 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('package'){
            steps{
            sh "mvn package "
            }
        }
        stage('Archiving'){
            steps{
            archiveArtifacts '**/target/*.jar'
            }
        }
    }
}
