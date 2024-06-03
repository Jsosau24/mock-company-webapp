pipeline {
  /*
   * TODO: Implement pipeline stages/steps
   *   See documentation: https://www.jenkins.io/doc/book/pipeline/syntax/#stages
   */

   agent any

    environment {
        NODE_OPTIONS = '--openssl-legacy-provider'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh './gradlew assemble'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './gradlew test'
                }
            }
        }
    }

    post {
        always {
            // This will always run, even if the build fails
            junit '**/build/test-results/test/*.xml'
            archiveArtifacts artifacts: '**/build/libs/*.jar', allowEmptyArchive: true
        }
    }
}