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
        stage('docker build'){
            steps{
            sh "docker build -t venkatakrishnareddy/docker-myapp:${BUILD_NUMBER} . "
            }
        }
        stage('docker login'){
            steps{
            withCredentials([string(credentialsId: 'DockerId', variable: 'DOCKER_PWD')]) {
            sh "docker login -u dvkr0439@gmail.com -p ${DOCKER_PWD}"
            }
            }
        }
        stage('docker push'){
            steps{
            sh " docker push venkatakrishnareddy/docker-myapp:${BUILD_NUMBER}"
            }
        }
        stage('Archiving'){
            steps{
            archiveArtifacts '**/target/*.jar'
            }
        }
    }
}
