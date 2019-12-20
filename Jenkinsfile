pipeline {
  agent any
  stages {
    stage('github') {
      steps {
        git(poll: true, url: 'https://github.com/dmmeteo/jenkins-dockerized.git', branch: 'master')
      }
    }

    stage('build_server') {
      parallel {
        stage('build_server') {
          steps {
            sleep 40
            echo 'build success'
          }
        }

        stage('build_client') {
          steps {
            sleep 50
            echo 'build success'
          }
        }

      }
    }

    stage('test1') {
      steps {
        sleep 60
        echo 'test success'
      }
    }

    stage('test2') {
      steps {
        sleep 60
        echo 'test success'
      }
    }

    stage('deploy') {
      steps {
        sleep 30
        echo 'deploy success'
      }
    }

  }
}