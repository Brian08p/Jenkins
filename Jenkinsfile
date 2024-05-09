pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo 'Stage 1: Build - Use tools like Maven or Gradle to compile and package the code.'
      }
    }

    stage('Unit and Integration Tests') {
      steps {
        echo 'Stage 2: Unit and Integration Tests - Use JUnit or TestNG for unit tests and Selenium for integration tests.'
      }
    }

    stage('Code Analysis') {
      steps {
        echo 'Stage 3: Code Analysis - Use SonarQube or Checkstyle to analyze code quality.'
      }
    }

    stage('Security Scan') {
      steps {
        echo 'Stage 4: Security Scan - Use tools like OWASP Dependency-Check or Snyk to identify vulnerabilities.'
      }
    }

    stage('Deploy to Staging') {
      steps {
        echo 'Stage 5: Deploy to Staging - Deploy to a staging server using Ansible or Jenkins Deploy Plugin.'
      }
    }

    stage('Integration Tests on Staging') {
      steps {
        echo 'Stage 6: Integration Tests on Staging - Run tests on the staging environment using Selenium or Postman.'
      }
    }

    stage('Deploy to Production') {
      steps {
        echo 'Stage 7: Deploy to Production - Deploy to a production server using Ansible or Jenkins Deploy Plugin.'
      }
    }
  }

  post {
    success {
      mail to: 'pereira.08brian@gmail.com',
           subject: "Pipeline Success: ${currentBuild.fullDisplayName}",
           body: "The pipeline ${currentBuild.fullDisplayName} has succeeded."
    }
    failure {
      mail to: 'pereira.08brian@gmail.com',
           subject: "Pipeline Failure: ${currentBuild.fullDisplayName}",
           body: "The pipeline ${currentBuild.fullDisplayName} has failed. Please check logs."
    }
  }
}

