pipeline {
  agent {
      docker {
          image 'maven:3.5.4-jdk-10-slim'
          args '-v $HOME/.m2:/root/.m2'
      }
  }
  parameters {
    string(defaultValue: "full", description: 'What Testing Type?', name: 'TestingType')
    choice(choices: ['smoke', 'full'], description: 'What Testing Type - Multiple Choices', name: 'TestingTypeMultipleChoice')
    booleanParam(name: 'nightly', defaultValue: false, description: '')    
  }
  stages {
    stage('Build Project') {
      steps {
          echo "${params.nightly}"
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
        echo "Testing Type: ${params.TestingType}"
        echo "TT from Multiple Choice: ${params.TestingTypeMultipleChoice}"
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