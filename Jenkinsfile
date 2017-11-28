pipeline {
  stages {
    stage('Test') {
      agent {
        docker {
        image 'golang'
        }
      }
      steps {
        sh 'go test'
      }
    }
  stage('Build') {
     agent {
      dockerfile true 
       }
    steps {
      
      script {
        def customImage = docker.build("capensis/math:${env.BUILD_ID}")
        customImage.push()
        customImage.push("latest")
      }
    }
  }
}
}