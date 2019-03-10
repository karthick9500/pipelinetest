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

      stage('Deployment to DEV') {

            steps {
                script{
                  println "Deploying to DEV"
                  println "Done"
                }
            }
        }

        stage('Approve deployment to QA') {
          when {
              environment name: 'ENV_DEPLOY', value: 'Deploy-to-QA'
          }
                steps {
                    timeout(604800) {
                        script {
                            input message: 'Do you want to deploy SIT', OK: true, submitter: "twst@test.com,test"
                            env.DEPLOY_TO_SIT = 'true'

                              println "Deploying to DEV"
                              println "Done"

                        }
                    }
                }
            }

            stage('Deploy to QA') {
              when {
                  environment name: 'DEPLOY_TO_SIT', value: 'true'
              }
                    steps {

                            script {

                                  println "Deploying to QA"
                                  println "Done"

                            }
                        }
                    }
                }


  }

  }
