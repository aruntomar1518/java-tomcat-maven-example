pipeline {
    agent any
    stages {
        stage ('Build Project') {
            steps {
                
                sh 'mvn clean package'
                
            }
        

            Post{
                success{
                    echo 'Now Archiving ...'

                    archiveArtifacts artifacts : '**/*.war'
                }
            }
        }
    }
}
