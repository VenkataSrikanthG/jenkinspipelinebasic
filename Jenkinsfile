pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building the core .Net application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the application'
            echo "Add Chromedriver ${ChromeDriverPath}"
          }
        }

        stage('Test log') {
          steps {
            writeFile(file: 'LogTestFile.txt', text: 'This is an automation log file.')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to Deploy?', id: 'OK')
            echo 'Deploying the application on the IIS servers'
          }
        }

        stage('Artifact') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Drivers\\Pathname'
  }
}