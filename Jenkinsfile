pipeline {
  agent none
  stages {
    stage('Test') {
      agent {
        docker {
<<<<<<< HEAD
        image 'golang' args '-u root --privileged'
=======
          image 'golang'
>>>>>>> 6d84adaf7929931f92fb6b2097c1bd8e1a4d57fc
        }

      }
      steps {
        echo 'skipping go'
      }
    }
    stage('Deploy') {
      steps {
        script {
          def customImage = docker.build("bdubois/maths:${env.BUILD_NUMBER}")
          docker.withRegistry('https://registry.hub.docker.com', 'Docker') {
            customImage.push("${env.BUILD_NUMBER}")
            customImage.push("latest")
          }
        }

      }
    }
  }
<<<<<<< HEAD
}
}
=======
}
>>>>>>> 6d84adaf7929931f92fb6b2097c1bd8e1a4d57fc
