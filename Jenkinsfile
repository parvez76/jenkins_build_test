pipeline {
  agent { label 'jenkins-agent' }
  tools {
    jdk 'java17'
    maven 'maven3'
  }
  stages {
    stage("Cleaning Up Workspaces") {
      steps {
        cleanWs()
      }
    }

    stage("Checkout from SCM") {
      steps {
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/parvez76/jenkins_build_test'
      }
    }

    stage("Build App") {
      steps {
        sh "mvn clean package"
      }
    }

    stage("Test App") {
      steps {
        sh "mvn test"
      }
    }
  }
}
