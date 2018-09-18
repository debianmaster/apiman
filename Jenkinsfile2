pipeline {
            agent {
              label 'maven'
            }
            stages {
              stage('Build App') {
                steps {
                  sh "mvn clean install -DskipTests=true"
                      script {
                         openshift.newBuild("--name=apiman-img", "--image-stream=docker.io/openshift/wildfly-110-centos7", "--binary=true")
                      }
                }
              }
            }
       }
