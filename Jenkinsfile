pipeline {
    agent any
        environment {
        mavenHome = tool 'mavenjenkins1'
        dockerHome = tool 'dockerjenkins'
        PATH= "${mavenHome}/bin:${dockerHome}/bin:${PATH}"
       }
    stages {
        stage('Info'){
                    steps {
                            echo "$env.JOB_NAME"
                            echo "$env.BUILD_NUMBER"
                            echo "$env.BUILD_ID"
                            echo "$env.BUILD_URL"
                            echo "welcome"



                    }
        }


        stage('compile'){
                    steps {
                            sh "mvn clean compile"

                    }
        }
        stage('Test'){
                    steps {
                            sh "mvn test"
                    }
        }
        stage('Package'){
                    steps {
                            sh "mvn package -DskipTests"
                    }
        }
    }
    post {
          always{
               echo "always"
          }
          success{
               echo "success"
          }
          failure{
               echo "failure"
          }

    }
}
