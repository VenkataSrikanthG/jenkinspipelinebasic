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
            echo "Add Chromedriver $(ChromeDriverPath)"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying the application on the IIS servers'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Drivers\\Pathname'
  }
}