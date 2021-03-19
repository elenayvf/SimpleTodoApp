pipeline {
  environment {
    imagename = "elenayvf/simple-todo-app"
    registry = "elenayvf/simple-todo-app"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/elenayvf/SimpleTodoApp.git', branch: 'main', credentialsId: 'GitHubCredentials'])

      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build imagename
        }
      }
    }
    stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( '', registryCredential ) {
            dockerImage.push("$BUILD_NUMBER")
             dockerImage.push('latest')

          }
        }
      }
    }
    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $imagename:$BUILD_NUMBER"
         sh "docker rmi $imagename:latest"

      }
    }
  }
}
      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build imagename
        }
      }
    }
    stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( '', registryCredential ) {
            dockerImage.push("$BUILD_NUMBER")
             dockerImage.push('latest')

          }
        }
      }
    }
    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $imagename:$BUILD_NUMBER"
         sh "docker rmi $imagename:latest"

      }
    }
  }
}-ipeline {
  environment {
    imagename = "elenayvf/simple-todo-app"
    registry = "elenayvf/simple-todo-app"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/elenayvf/SimpleTodoApp.git', branch: 'main', credentialsId: 'GitHubCredentials'])

      }
    }
    stage('Building image') {
      steps{
        sh "docker build -t getting-started ."
      }
    }
    stage('Deploy Image to Dockerhub') {
      steps{
        sh "docker tag getting-started $imagename"
        sh "docker push $imagename"
        }
      
    }
    stage ('Pull image and run in container'){
      steps{
          sh "docker pull $imagename:latest"
          sh "docker run -dp 3000:3000 $imagename"
        }
    }
    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $imagename:$BUILD_NUMBER"
         sh "docker rmi $imagename:latest"

      }
    }
  }
}-ipeline {
  environment {
    imagename = "elenayvf/simple-todo-app"
    registry = "elenayvf/simple-todo-app"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'https://github.com/elenayvf/SimpleTodoApp.git', branch: 'main', credentialsId: 'GitHubCredentials'])

      }
    }
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build imagename
        }
      }
    }
    stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( '', registryCredential ) {
            dockerImage.push("$BUILD_NUMBER")
             dockerImage.push('latest')

          }
        }
      }
    }
    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $imagename:$BUILD_NUMBER"
         sh "docker rmi $imagename:latest"

      }
    }
  }
}
