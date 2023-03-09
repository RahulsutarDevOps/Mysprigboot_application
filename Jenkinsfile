pipeline {
    agent any 
    stages {
        stage('Compile and Clean') { 
            steps {
              
                sh "mvn clean compile"
            }
        }
        stage('deploy') { 
            
            steps {
                sh "mvn package"
            }
        }
        stage('Build Docker image'){
          
            steps {
                sh 'docker build -t  sutarrahul/app_deploy:${BUILD_NUMBER} .'
            }
        }
        
        stage('Docker deploy'){
            steps {
               
                sh 'docker run -itd -p  8081:8080 sutarrahul/app_deploy:${BUILD_NUMBER}'
            }
        }
        stage('Archving') { 
            steps {
                 archiveArtifacts '**/target/*.jar'
            }
        }
    }
}























// pipeline {
   // agent {
   // node {
        //label 'dev'
     //   customWorkspace '/home/ec2-user/gitdir/springboot-hello'
    // }
// } 
    
     //stages {
       // stage('Compile and Clean') { 
       //     steps {
                // Run Maven on a Unix agent.
              
         //       sh "mvn clean compile"
          //  }
      //  }
         //stage('deploy') { 
            
           // steps {
             //   sh "mvn package"
         //   }
     //   }
        // stage('Build Docker image'){
          
           // steps {
             //   echo "Hello Java Express"
               // sh 'ls'
                //sh 'docker build -t  sutarrahul/docker_jenkins_springboot:${BUILD_NUMBER} .'
        //    }
     //   }
        // stage('Docker Login'){
            
           // steps {
             //    withCredentials([string(credentialsId: 'Dockerid', variable: 'Dockerpwd')]) {
               //     sh "docker login -u sutarrahul -p ${Dockerpwd}"
           //     }
         //   }                
     //   }
        // stage('Docker Push'){
           // steps {
             //   sh 'docker push sutarrahul/docker_jenkins_springboot:${BUILD_NUMBER}'
          //  }
      //  }
        //stage('Docker deploy'){
          //  steps {
               
            //    sh 'docker run -itd -p  8081:8080 sutarrahul/docker_jenkins_springboot:${BUILD_NUMBER}'
         //   }
      //  }
        // stage('Archving') { 
           // steps {
             //    archiveArtifacts '**/target/*.jar'
         //   }
    //    }
 //   }
// }





