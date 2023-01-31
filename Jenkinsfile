pipeline {
  agent { label 'linux'}
  options {
    buildDiscard(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOCKERHUB_CREDENTALS = credentals("danialkarim')
  }
  stages {
    stage ("check out"){
      steps{
          git branch: './main', url: 'https://github.com/danialkarim807/Rassignment.git'            }
       }
    }
    stage ("build"){
      steps{
          sh 'docker build -t danialkarim807/assi:img .'
            }
        }
    stage ("login"){
      steps{
          sh 'echo $DOCKERHUB_CREDENTALS_PEW | docker login -u $DOCKERHUB_CREDENTALS_USR --password-stdin   '
            }
        } 
    stage ("push"){
      steps{
          sh 'docker push danialkarim807/assi:img '
            }
        } 
     }
post {
  always {
    sh 'docker logout'
   }                                 
  }
}
                                      
        // stage('Build and Push Docker Image') {
        //     steps {
        //         git branch: '', url: 'https://github.com/danialkarim807/Rassignment.git'
        //             sh 'docker login -u danialkarim8@gmail.com -p --password-stdin.'
        //             sh 'docker build -f Dockerfile -t danialkarim807/assignment:img .'
        //             sh 'docker push danialkarim807/assignment:img'
                
                //dir('./') {
                  //  sh 'docker build -f Dockerfile -t danialkarim807/assignment:img .'
                //    sh 'docker push danialkarim807/assignment:img'
        //        }
                // sh 'docker compose -f docker compose.yaml build'
                // sh 'docker compose -f docker compose.yaml push'
//             }
//         }

    


