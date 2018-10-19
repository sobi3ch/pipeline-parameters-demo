pipeline {
  agent any
  parameters {
    choice(name: 'upstream_platform',
            choices: 'v6 (latest)\nv7-dev.12341abc\nv5\nv4\nv3\nv3dev\nv2\nv2dev\nv1',
            description: 'Pickup version to deploy?')
    choice(name: 'profiles',
            choices: 'v3 (latest)\nv4-dev.asdf1234\nv2\nv1',
            description: 'Pickup version to deploy?')
    choice(name: 'session',
            choices: 'v5 (latest)\nv6-dev.d832k38ck\nv4\nv3\nv2\nv1',
            description: 'Pickup version to deploy?')
  }
  stages {
    stage('Prepare') {
      steps {
        echo "Upstream platform: ${params.upstream_platform}"
        echo "Profiles: ${params.profiles}"
        echo "Session: ${params.session}"
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
        echo "Terraform will perform the following actions:

  + aws_db_instance.default
     ...
      password:                   <sensitive>
      username:                   "foo"

Plan: 3 to add, 1 to change, 1 to destroy."
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
        echo "Deploying to ${params.env}"
        sh "sleep 3"
      }
    }
  }
}
