pipeline {
     agent { label 'ec2-agent' } 

    environment {
        GITHUB_CREDENTIALS = credentials('github-credentials') // ID from Jenkins
        REPO_URL = 'https://github.com/jogeshniwalkar/gs-spring-boot-s2.git'
        BRANCH = 'develop'
    }

    stages {
        stage('Checkout') {
            steps {
                git(
                    url: "https://github.com/jogeshniwalkar/gs-spring-boot-s2.git",
                    branch: "${BRANCH}"
                )
            }
        }

        stage('Build') {
            steps {
                echo "Running build......."
                // Add your build steps here
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                // Add your test commands here, e.g., pytest
            }
        }

        stage('Push Changes') {
            steps {
                script {
                      echo "test"
                    // sh """
                    // git config user.name "Jenkins"
                    // git config user.email "jenkins@example.com"
                    // git add .
                    // git commit -m "Automated commit from Jenkins"
                    // git push https://${GITHUB_CREDENTIALS}@github.com/<username>/<repo>.git ${BRANCH}
                    // """
                }
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
