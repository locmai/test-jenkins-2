pipeline {
  agent {
      docker {
          image 'maven:3.5.4-jdk-10-slim'
          args '-v $HOME/.m2:/root/.m2'
      }
  }
  stages {
    stage('Build Project') {
      steps {
          echo "Building project ..."
      }
    }
    stage('Code Analysis') {
      steps {
          echo "Scanning with Sonar ..."
      }
    }
    stage('Integration Test') {
      steps {
          echo "Start running tests ..."
      }
    }
    stage('Publish Dev Packages') {
      steps {
          echo "Publishing Dev Packages ..."
      }
    }
    stage('Deploy Approval'){
      steps {
        input "Deploy to Testing environment?"
      }
    }
    stage('Trigger Deploy job') {
      steps {
        echo "Triggering Deploy job ... "
      }
    }
    stage('Clean up') {
      steps {
        echo "Have a nice day!"
      }
    }
  }
}