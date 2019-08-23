pipeline {
    agent any
    stages {
        stage ('Build Servlet Project') {
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
