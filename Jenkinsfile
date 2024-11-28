pipeline { 
    agent any 
    stages { 
        stage("Checkout /Clone from Git & Maven Build") { 
            steps { 
                      git branch: "Main" ,   url : "https://github.com/devopsusergit/PetStoreWebApp.git"
                      sh  'mvn clean'
                      sh  ' mvn package'
            } 
        } 
        stage('Clean and Package') {
        steps {
        echo 'Cleaning workspace and packaging'
        sh 'mvn clean package'

        }

        }

           stage('Parallel Tasks') {
              parallel {
        stage('Performance Testing') {
            steps{
            echo 'Running performance tests'
          }
         }
       stage('Code Quality Check') {
         steps {
         echo 'Running code quality checks'
         }
        }
     }
}
        stage('Stage 3') {
      steps {
        script {
          echo 'This is for stage 3 assessment.'
        }
      }
    }
    stage('Regression Acceptance Testing') {
       stages {
        stage('Regression Testing') {
        steps {
        echo 'Running regression tests'
    }
  }
     stage('Acceptance Testing') {
        steps {
        echo 'Running acceptance tests'
       }
      }
     }
    }  
  }
}
