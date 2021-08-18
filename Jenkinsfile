  - script: >
      folder('JenkinsAsCode-TestDevOps')
  - script: >
      pipelineJob('JenkinsAsCode-TestDevOps/demo77-docker-sample-run') {
        parameters {
          textParam('myParameterName', 'my default textParam value', 'my description')
        }
        definition {
          cps {
            script("""\
              pipeline {
                agent any
                stages('Global') {
                  stage('Build') {
                    steps {
                      sh " echo 'prueba 1'> /tmp/fichero1.txt"
                      sh " docker run --name prueba1 hello-world"
                      sh " docker rm -f prueba1"
                      sh script:'''
                        #!/bin/bash
                        echo "This is start \$(pwd)"
                        echo "This is \$(pwd)"
                        echo \$myParameterName
                        '''
                    }
                  }
                }
              }""".stripIndent())
            sandbox(true)
          }
        }
      }
