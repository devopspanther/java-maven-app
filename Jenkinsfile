def gv

pipeline {
    agent any
    tools {
        maven 'maven-3.8' 
    }

    stages {
        stage("init") {
            steps {
                script {
                   gv = load "script.groovy"
                }
            }
        }
        stage('Build Jar') {
            steps {
                script {
                     gv.buildJar()
                }
            }
        }
        stage('Build image') {
            steps {
                script {
                    gv.buildImage()
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
                script {
                    gv.eployApp()
                }
            }
        }
    }
}
