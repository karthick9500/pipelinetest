pipeline {
    agent any
    parameters {
      choice(choices: 'all\nbuild\nDeploy-to-DEV\nDeploy-to-QA\n', description: 'Please select the environment ', name: 'ENV_DEPLOY')
    }

  stages {



    stage('test') {
      script {
        sh "ls -la"
      }
    }

     }
  }
