pipeline {
   agent any

   stages {
      stage('SCM') {
          steps {
              echo 'Check out scripts from GitHub'
              git 'https://github.com/CamperDave2016/pipeline_scripts.git'
          }
      }
      stage('Build') {
         steps {
            echo 'Start building...'
            bat 'build.bat'
         }
      }
      stage('NUnit') {
          steps {
            echo 'Start NUnit testing...'
            bat 'nunit.bat'
          }
      }
      stage('Deploy') {
          steps {
echo 'Start Deploy...' 
             bat 'deploy.bat'
          }
      }
   }
   
   post {
       always {
           echo 'This will always run'
       }
       success {
           echo 'This will run if success'
       }
       failure {
           echo 'This will run if fails'
       }
       unstable {
           echo 'This will run if it is marked unstable'
       }
       changed {
           echo 'This will run if state changed'
       }
   }
}
