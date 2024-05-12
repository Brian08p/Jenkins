pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    try {
                        sh "echo 'Stage 1: Build - Use tool like Maven to compile and package the code.' > build.log"
                    } catch (Exception e) {
                        echo "Failed to execute shell command: ${e.getMessage()}"
                    }
                }
            }
        }
    }

    stage('Unit and Integration Tests') {
        steps {
            script {
                
                sh "echo 'Stage 2: Unit and Integration Tests - Using TestNG for unit tests and Selenium for integration tests.' >> build.log"
            }
        }
    }

    stage('Code Analysis') {
        steps {
            script {
                sh "echo 'Stage 3: Code Analysis - Using Checkstyle to analyze code quality.' >> build.log"
            }
        }
    }

    stage('Security Scan') {
        steps {
            script {
                sh "echo 'Stage 4: Security Scan - Using tools like OWASP Dependency-Check to identify vulnerabilities.' >> build.log"
            }
        }
    }

    stage('Deploy to Staging') {
        steps {
            script {
                sh "echo 'Stage 5: Deploy to Staging - Deploy to a staging server using Jenkins Deploy Plugin.' >> build.log"
            }
        }
    }

    stage('Integration Tests on Staging') {
        steps {
            script {
                sh "echo 'Stage 6: Integration Tests on Staging - Run tests on the staging environment using Selenium.' >> build.log"
            }
        }
    }

    stage('Deploy to Production') {
        steps {
            script {
                sh "echo 'Stage 7: Deploy to Production - Deploy to a production server using Ansible or Jenkins Deploy Plugin.' >> build.log"
            }
        }
    }
}

    post {
        always {
            emailext(
                to: 'pereira.08brian@gmail.com',
                subject: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build #${env.BUILD_NUMBER}",
                body: "The pipeline ${currentBuild.fullDisplayName} has ${currentBuild.currentResult}. Please see attached logs.",
                attachmentsPattern: "**/build.log"
            )
        }
    }
}
