pipeline {
    agent any
    parameters{
        choice(name:'VERSION',choices:['1','2'], description:'che versione')
        booleanParam(name:'execTests',defaultValue:True, description:'faccio i tests?')
        string(name:'WHOIS',defaultValue:'Non sono stato io',description:'chi è stato a farlo?')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.. è stato ${params.WHOIS}"
            }
        }
        stage('Test') {
            when{
                expression{
                    BRANC_NAME == 'main' || params.execTests == True
                }
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying.... versione: ${params.VERSION}"
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
