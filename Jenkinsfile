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

        stage('Deploy to staging') {

            steps {

                /* One nice thing about calling a job from the pipeline is that we can change the target for the jobs per environment and then use the same Jenkins file for each. */
                
                build job: 'deploy-to-staging'

            }

        }

    }
}