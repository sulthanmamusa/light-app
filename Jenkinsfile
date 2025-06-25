pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile'
    }
  }

  environment {
    CHROME_BIN = '/usr/bin/chromium-browser'
  }

  stages {
    stage('Build') {
      steps {
        sh 'npx ng build --configuration production'
      }
    }

    stage('Test') {
      steps {
        sh 'npx ng test --watch=false --browsers=ChromeHeadlessNoSandbox'
      }
    }
  }
}
