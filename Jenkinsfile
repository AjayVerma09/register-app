pipeline {
    agent { label 'Jenkins-Agent' }
    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }
    stages{
       stage("Cleanup Workspace"){
               steps {
                    cleanWS()
               }
       }

       stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'github', url: 'https://github.com/AjayVerma09/register-app.git'
                }
       } 
       
       stage("Build Application"){
                steps {
                    sh "mvn clean package"
                }

       }

       stage("Test Application"){
                steps {
                    sh "mvn test"
                }
       }  
    }
}
