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
        stage("build") {
            steps {
                sh 'mvn clean install'
            }
        }
       }
} 
		
