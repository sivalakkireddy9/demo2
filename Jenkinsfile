pipeline {
    agent any
          stages {
              stage('clone project') {
                                    steps {
                      git branch:'master',
                      url:'https://github.com/sivalakkireddy9/demo2'                                    
                                             }
                                    }
        
              stage('build') {
                                steps {
                                    sh 'mvn clean install'
                                    }
                            }
          }        
        post {
        success {
            emailext(
                subject: "Build Success: ${currentBuild.fullDisplayName}",
                body: "The build ${env.BUILD_URL} was successful!",
                to: "sivalakkireddy999@gmail.com"
            )
        }
        failure {
            emailext(
                subject: "Build Failed: ${currentBuild.fullDisplayName}",
                body: "The build ${env.BUILD_URL} failed. Please check.",
                to: "sivalakkireddy999@gmail.com"
            )
        }
     }
   }
