pipeline {
    agent any
    stages {
        stage('Build'){
            steps {
                echo 'STARTING'
                git url: 'https://bitbucket.org/jjimenez-ind/complete_own_project/src/main/'
                echo 'Cleaning and packaging with maven...'

                withMaven {
                    bat 'mvn clean package'
                }
            }

            post{
                success{
                    echo 'DONE'
                }

                failure {
                    echo 'FAILED'
                }
            }
        }
    }
}