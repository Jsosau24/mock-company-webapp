pipeline {
  /*
   * TODO: Implement pipeline stages/steps
   *   See documentation: https://www.jenkins.io/doc/book/pipeline/syntax/#stages
   */

   agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // TODO: Add the build step
                    sh './gradlew assemble'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // TODO: Add the test step
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
