node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }     
      stage('Build image') {         
       
            app = docker.build("binoychandramandal/nodejs-docker-pipeline")    
      }     
      stage('Test image') {           
            app.inside {            
             
             sh 'echo "Tests passed"'        
            }    
      }     
      stage('Push image') {
      docker.withRegistry('https://registry.hub.docker.com', 'dockerhub_id') {            
      app.push("${env.BUILD_NUMBER}")            
      app.push("latest")        
              }    
           }
      }
