pipeline {
    agent any
    parameters {
      choice(choices: 'all\nbuild\nDeploy-to-DEV\nDeploy-to-QA\n', description: 'Please select the environment ', name: 'ENV_DEPLOY')
    }

    stages {


    // Stage 1
    stage("Init"){
       steps
      {
        sh 'echo "Initialize"'
        sh 'echo ${ENV_DEPLOY}'
      }
    }
  }

  }
