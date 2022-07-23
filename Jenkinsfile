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
}