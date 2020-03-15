pipeline {
    agent any

    stages {
        stage('CheckOut') {
            steps {
                echo 'Check out code.'
                git credentialsId: 'f26a48a2-e35d-4318-9839-18f31fa34c11', url: 'https://github.com/springheeledjackDE/WebApplication1.git'
                stash name: 'checkedOutCode',
                    includes: '*.*'
            }
        }
        stage('Unstash To Node3 b') {
            agent { node { label 'Node3' } }
            steps {
                unstash name: 'checkedOutCode' }
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