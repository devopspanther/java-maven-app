#!/usr/bin/env groovy

def gv

pipeline {
    agent any

    stages {
        stage('Init') {
            steps {
                script {
                     gv = load 'script.groovy'
                }
            }
        }
        stage('Build') {
            steps {
                script {
                     gv.buildApp()
                }
            }
        }
        stage('Test') {
            steps {
                script {
                   gv.testApp()
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                     gv.deployApp()
                }
            }
        }
    }
}
