pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Testing..'
                echo "Executing pipeline for branch $BRANCH_NAME .."
            }
        }
        stage('Build') {
            when {
                expression {
                    BRANCH_NAME == 'master'
                }
            }
            steps {
                echo 'Building..'
            }
        }
        stage('Deploy') {
            when {
                expression {
                    BRANCH_NAME == 'master'
                }
            }
            steps {
                echo 'Deploying to dev enviroment....'
            }
        }
    }
}
