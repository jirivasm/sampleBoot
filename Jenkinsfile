pipeline {
    agent any
    //     environment {
    //     ENV_DOCKER = credentials('dockerhub')
    //     DOCKERIMAGE = "dummy/dummy"
    //     EKS_CLUSTER_NAME = "demo-cluster"
    // }
    stages {
        stage('build') {
            agent {
                docker { image 'openjdk:11-jdk' }
            }
            steps {
                sh 'chmod +x gradlew && ./gradlew build jacocoTestReport'
            }
        }
        stage('sonarqube') {
        //  agent {
        //      docker { image 'sonarqube:8.9.9-community' } }
            steps {
                sh 'echo scanning!'
            }
        }
        stage('docker build') {
            steps {
                sh 'echo docker build'
            }
        }
        stage('docker push') {
            steps {
                sh 'echo docker push!'
                }
            }
        stage('Deploy App') {
            steps {
                sh 'echo deploy to kubernetes'               
            }
        }
    }
} 
