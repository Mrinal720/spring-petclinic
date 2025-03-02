//node('Primary') {
//  stage ('Source code'){
//    git branch: 'main', url: 'https://github.com/Mrinal720/spring-petclinic.git'    
//   }
    
//   stage ('Build code'){
//    sh 'mvn clean package'
//   }
   
//   stage ('Archiving artifacts'){
//     junit stdioRetention: '', testResults: '**/surefire-reports/*.xml'
//     archiveArtifacts artifacts: '**/*.war', followSymlinks: false
//   }
//}

pipeline {
     agent { label 'Primary' }
     
     options{
         retry(3)
         timeout(time: 1, unit: 'HOURS') 
    } 
      triggers {
        cron('0 * * * *')
    }
    
  stages{  
  stage ('Source code'){
    steps{
    git branch: 'main', url: 'https://github.com/Mrinal720/spring-petclinic.git'
   }
  }

   stage ('Build code'){
    steps{
   sh 'mvn clean package'
   }
  }

   stage ('Archiving artifacts'){
    steps{
     junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
    }
  }
  }
  
 post{
   success{
      echo "build successfull" 
    }
   unsuccessful{
     echo "failure" 
  }
 }
}
     


