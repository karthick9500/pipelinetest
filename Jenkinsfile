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
        sh 'echo $ENV_DEPLOY'
      }
    }

    stage('Approve deployment to SIT') {

            steps {
                timeout(604800) {
                    script {
                        input message: 'Do you want to deploy SIT', OK: true, submitter: "test"
                        env.DEPLOY_TO_SIT = 'true'
                    }
                }
            }
        }






  }

  }
