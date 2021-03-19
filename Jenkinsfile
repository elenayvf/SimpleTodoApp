pipeline {
  environment {
    imagename = "elenayvf/simple-todo-app"
    registry = "elenayvf/simple-todo-app"
    registryCredential = 'dockerhub'
    dockerImage = ''
  }
 
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
