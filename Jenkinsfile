pipeline { 
    agent any 
    stages { 
        stage("Check") { 
            steps { 
                      git branch: "Main" ,   url : "https://github.com/devopsusergit/PetStoreWebApp.git"
                      sh  'mvn clean'
                      sh  ' mvn package'
            } 
        } 
        stage('Package') {
        steps {
        echo 'Cleaning workspace and packaging'
        sh 'mvn clean package'

        }

        }


        stage('Test') {
      steps {
        script {
          echo 'This is for stage 3 assessment.'
        }
      }
    }
        stage('Parallel') {
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
        stage('Sequence'){
         stages{          
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
}
}



                                                            






                                                       
