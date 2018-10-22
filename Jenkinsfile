pipeline {
  agent any
  parameters {
    choice(name: 'env',
            choices: 'stage-US\nstage-EU\nPRODUCTION',
            description: 'Environment you want deploy to')
    choice(name: 'version',
            choices: 'v9.3.1 (latest)\nv9.4.0-dev.eixk3sik\nv9.3.0\nv9.2.2',
            description: 'Version you want to deploy')
  }
  stages {
    stage('Prepare') {
      steps {
        echo "Environemt: ${params.env}"
        echo "Version: ${params.version}"
        sh "sleep 1"
      }
    }

    stage('Coding Standards') {
      steps {
        echo "Checking coding standards.."
        sh "sleep 1"
      }
    }

    stage('Run tests') {
      steps {
        echo "Running tests.."
        sh "sleep 1"
      }
    }

    stage('Terraform plan') {
      steps {
        echo '''
        Terraform will perform the following actions:

  + aws_db_instance.default
     ...
      password:                   <sensitive>
      username:                   "foo"

Plan: 3 to add, 1 to change, 1 to destroy.
'''
        sh "sleep 2"
      }
    }

    stage('Deploy') {

      input{
        message "Do you want continue deployment?"
        ok "Continue deployment"
        // parameters {
        //   string(name:'username', defaultValue: 'user', description: 'Username of the user pressing Ok')
        // }
      }

      steps {
        echo "Deploying to ${params.env}; version ${params.version}"
        sh "sleep 3"
      }
    }
  }
}
