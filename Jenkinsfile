pipeline {
  agent any
  environment {
    IMAGE_CONTAINER = "local_trivy:latest"
  }
  stages('Global') {
    stage('Build') {
      steps {
        sh " echo 'prueba 1'> /tmp/fichero1.txt"
        sh " docker run --name prueba1 $IMAGE_CONTAINER"
        sh " docker rm -f prueba1"
        sh script:'''
          #!/bin/bash
          echo "This is start $(pwd)"
          echo "This is $(pwd)"
          '''
      }
    }
  }
}
