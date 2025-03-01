node('Primary') {
   stage ('Source code'){
    git branch: 'main', url: 'https://github.com/Mrinal720/spring-petclinic.git'    
   }
    
   stage ('Build code'){
    sh 'mvn clean package'
   }
   
   stage ('Archiving artifacts'){
     junit stdioRetention: '', testResults: '**/surefire-reports/*.xml'
     archiveArtifacts artifacts: '**/*.war', followSymlinks: false
   }
}
   
  
