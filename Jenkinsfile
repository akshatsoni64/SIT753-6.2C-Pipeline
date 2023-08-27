pipeline {
    agent any

    stages {
        stage('Build') {
            environment{
                DIRECTORY_PATH = ''
            }
            steps {
                echo 'Fetcing the source code from ${env.DIRECTORY_PATH}'
                echo 'Compiling the code and generating artifacts...'
                sleep 5
                echo 'Done'
            }
            post{
                success{
                    mail to: "s223712753@deakin.edu.au",
                    subject: "Build Status Email",
                    body: "Build was successful!"
                }
            }
        }
    }
}