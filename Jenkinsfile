pipeline {
  agent any
  parameters {
    choice( name: 'env',
            choices: 'stage-eu\nstage-us\nprod-eu\nprod-us',
            description: 'Pickup deployment environment')
    choice(name: 'upsteram_platform',
            choices: 'v6 (latest)\nv5\nv4\nv3\nv3dev\nv2\nv2dev\nv1',
            description: 'Pickup upstream version to deploy?')
    choice(name: 'profiles',
            choices: 'v3 (latest)\nv2\nv1',
            description: 'Pickup upstream version to deploy?')
    choice(name: 'session',
            choices: 'v5 (latest)\nv4\nv3\nv2\nv1',
            description: 'Pickup session version to deploy?')
  }
  stages {
    stage('Prepare') {
      steps {
        echo "Environment: ${params.env}"
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

    stage('Deploy') {
      steps {
        echo "Deploying to ${params.env}"
        sh "sleep 3"
      }
    }
  }
}
