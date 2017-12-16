pipeline {
    agent any
    stages{

        stage('Build'){
            steps {
                sh '/Users/alirodell/Documents/Dev/maven/apache-maven-3.5.0/bin/mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

    }
}