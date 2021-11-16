pipeline {
    agent any
    stages {
        stage('Build'){
            steps {
                git url: 'https://bitbucket.org/jjimenez-ind/complete_own_project/src/main/'
                echo 'Cleaning and packaging with maven...'

                withMaven {
                    bat 'mvn clean package'
                }
            }

            post{
                success{
                    echo 'DONE'
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                    echo 'Archived'
                }

                failure {
                    echo 'FAILED'
                }
            }
        }
    }
}