pipeline {
  agent {
    label 'linux'
  }

  environment {
    ENV = 'local'
  }

  parameters {
    string(
      name: 'TAG_TO_DEPLOY',
      defaultValue: '',
      description: 'Manually specify a tag to build (e.g., "sit-v1.0.0")'
    )
  }

  options {
    skipDefaultCheckout()
  }

  stages {
    stage('Stage 1') {
      steps {
        echo 'Hello, world'
      }
    }
  }

  post {
    always {
      echo 'Pipeline completed'
      cleanWs()
    }
    success {
      echo 'Pipeline succeeded!'
    }
    failure {
      echo 'Pipeline failed!'
    }
    unstable {
      echo 'Pipeline is unstable'
    }
    changed {
      echo 'Pipeline state changed'
    }
  }
}
