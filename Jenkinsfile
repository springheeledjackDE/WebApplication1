pipeline {
    agent any

    stages {
        stage('CheckOut') {
            steps {
                echo 'Check out code 1.'
                git credentialsId: 'f26a48a2-e35d-4318-9839-18f31fa34c11', url: 'https://github.com/springheeledjackDE/WebApplication1.git'
               
            }
        }
        stage('Unstash To Node3 c') {
            agent { node { label 'Node3' } }
            steps {
                    checkout scm

                    def customImage = docker.build("my-image:${env.BUILD_ID}")

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