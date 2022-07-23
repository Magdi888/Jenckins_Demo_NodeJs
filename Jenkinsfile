#!/usr/bin/env groovy

def gv
pipeline {
    agent any
    stages {
        stage('start') {
            steps {
                script {
                     gv = load 'script.groovy'
                }
            }
        }
        stage('BuildImage') {
            steps {
                script {
                    gv.BuildImage()
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    gv.Deploy()
                }
            }
        }
    }
    post {
            success {
                slackSend (message:"Build deployed successfully - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)")
            }
            failure {
                slackSend (message:"Build failed  - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)")
            }
        }
}