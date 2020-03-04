pipeline {
  
  agent none
  
  stages {
    
    stage('Compilation et tests') {

      agent {
        label 'agent_java'
      }
  
     stage('Test unitaire & publication') {
    
       steps {
         sh 'mvn test'
          }
        }


        stage('Compilation') {
    
          steps {  
            sh 'mvn -B -DskipTests clean package'
          }
        }
            
        stage('Publication du binaire') {
          steps {
            sh "curl -u admin:Shaymin122 --upload-file target/*.war 'http://84.39.43.46:8081/repository/depot_test/rondoudou${BUILD_NUMBER}.war'"        
          }

        }
   
  }
}
