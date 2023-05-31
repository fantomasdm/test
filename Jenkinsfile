pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            when{
                expression{
                    BRANC_NAME == 'MAIN'
                }
            }
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
    post
    {
        always{
            echo 'sempre'
        }
        success{
            echo 'tutto bene'
        }
        failure{
            echo 'andata male'
        }
    }
}
