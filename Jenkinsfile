pipeline {
    agent any
    stages{
        stage(' clean and compile '){
            steps{
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
        stage('docker build and push'){
            steps{
                script{
                    withDockerRegistry(credentialsId: '2c14b8c6-e7ac-4fe2-8b69-1c2ac13305f3') {
                        sh "docker build -t venkatakrishnareddy/docker-myapp:${BUILD_NUMBER} . "
                        sh "docker push venkatakrishnareddy/docker-myapp:${BUILD_NUMBER}"
                       }
                       }
        }
        }
        stage('Archiving'){
            steps{
            archiveArtifacts '**/target/*.jar'
            }
        }
    }
}
