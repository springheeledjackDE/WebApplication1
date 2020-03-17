pipeline {
environment {
    registry = "springheeledjack/temp"
    dockerHubCredential = 'dockerHubCredentials'
    dockerImage = ''
  }
    agent any

    stages {
        stage('CheckOut') {
            steps {
                echo 'Check out code 1.'
                git credentialsId: 'f26a48a2-e35d-4318-9839-18f31fa34c11', url: 'https://github.com/springheeledjackDE/WebApplication1.git'
               
            }
        }
        stage('Building image on Node3') {
            agent { node { label 'Node3' } }
            steps {
                checkout scm

                script {
                    def customImage = docker.build(registry + ":${env.BUILD_ID}")
                    customImage.push()
                  
                }
            }
        }
        stage('Deploy Image on Node3') {
            steps{
                script {
                        docker.withRegistry( '', dockerHubCredential ) {
                        dockerImage.push()
                    }
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
	}
	stage('Kev') {
            steps {
                echo 'Keving....'
            }
        }
    }
}