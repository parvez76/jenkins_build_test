pipeline {
  agent { label 'Jenkins-Agent' }
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
        git branch: 'main', credentialId: 'github', url: 'https://github.com/parvez76/jenkins_deployment'
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
