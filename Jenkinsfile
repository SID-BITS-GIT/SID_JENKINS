pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    try {
                        echo 'Building application...'
                    } catch (Exception e) {
                        error "Build failed!"
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    try {
                        echo 'Running tests...'
                    } catch (Exception e) {
                        error "Tests failed!"
                    }
                }
            }
        }
        // stage('Build') {
        //     steps {
        //         echo "Building PR: ${env.CHANGE_ID} by ${env.CHANGE_AUTHOR}"
        //         // your build logic
        //     }
        // }
        // stage('Test') {
        //     steps {
        //         echo "Running tests for PR: ${env.CHANGE_ID}"
        //     }
        // }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
            }
        }

        stage('Deploy to Production') {
            steps {
                input 'Deploy to Production?'
                echo 'Deploying to Production...'
            }
        }
    }
    post {
        success {
            echo '✅ Pipeline completed successfully!'
            // mail to: '@wilp.bits-pilani.ac.in',
            //      subject: '✅ Jenkins Build Success',
            //      body: 'Good job! The Jenkins pipeline completed successfully.'
        }

        failure {
            echo '❌ Pipeline failed!'
            // mail to: '@wilp.bits-pilani.ac.in',
            //      subject: '❌ Jenkins Build Failed',
            //      body: 'Please check Jenkins logs for more information.'
        }
    }
}