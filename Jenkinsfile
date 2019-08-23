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

        stage ('Deploy Build in Staging Area'){
            steps{

                build job : 'Deploy Staging-Area Pipeline'
            }
        }
    }
}
