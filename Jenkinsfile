pipeline {
    agent any
    tools {
        maven 'maven-3.8' 
    }

    stages {
        stage('Build Jar') {
            steps {
                script {
                     echo 'Building application..'
                     sh 'mvn package'
                }
            }
        }
        stage('Build image') {
            steps {
                script {
                    echo 'Building application docker image..'
                    withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                            sh 'docker build -t akodevops/demo:jma-2.0 .'
                            sh "echo $PASS | docker login -u $USER --password-stdin"
                            sh 'docker push akodevops/demo:jma-2.0'
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
    }
}
