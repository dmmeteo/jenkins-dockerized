pipeline {
  agent any
  stages {
    stage('github') {
      steps {
        git(poll: true, url: 'https://github.com/dmmeteo/jenkins-dockerized.git', branch: 'master')
      }
    }

    stage('build') {
      parallel {
        stage('build_server') {
          steps {
            sleep 40
            echo 'build success'
            sh '''docker pull python:3.7.5
docker tag python:3.7.5 docker-registry:5000/python3:v1
docker push docker-registry:5000/python3:v1
'''
          }
        }

        stage('build_client') {
          steps {
            sleep 50
            echo 'build success'
            sh '''docker pull node:10.18.0
docker tag python:3.7.5 docker-registry:5000/node10:v1
docker push docker-registry:5000/node10:v1
'''
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