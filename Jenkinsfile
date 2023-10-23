pipeline {
    agent any

    stages {
        stage('Run Test'){
            steps{
                sh "docker-compose -f grid.yaml up -d"
            }
        }
        stage('Run Test'){
            steps{
                sh "docker-compose -f test-suites.yaml up"
            }
        }
    }

    post {
        always {
            sh "docker-compose -f grid.yaml up down"
            sh "docker-compose -f test-suites.yaml down"
        }
    }
 
}