pipeline {
      agent any
      environment { 
		PATH= "/opt/maven/bin:$PATH"
      }
      stages {
	stage("stage1") {
	   steps {
             git url: "https://github.com/venkatesansadasivam/webapp-project.git" , branch: 'main'
           }
        }
        stage("bulid") {
           steps {
             sh 'mvn clean deploy'
           }
        }
        stage("sonarqube analysis") {
          environment {
                 scannerHome = tool 'saidemy-sonarqube-scnner'
          }
          steps {
                withSonarQubeEnv('saidemy-sonarqube-server') {
                 sh "${scannerHome}/bin/sonar-scanner"
                 }
           }
         }

        }
        }
   
		
