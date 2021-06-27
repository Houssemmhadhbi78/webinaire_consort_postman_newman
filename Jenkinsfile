pipeline {
    agent any
	tools{nodejs "nodejs"}
    stages {
		stage("Newman package installation") {
            steps{
				sh 'npm install - g newman'
			}
		}
        stage("Run Newman") {
            
			steps {
                //sh for LINUX and bat for Windows
				script{
					try{
						sh 'newman run TestAPI_Jenkins.postman_collection.json -e QA.postman_environment.json -r junit,cli --reporter-junit-export newman.xml'
							currentBuild.result= 'SUCCESS'
					}catch(exception ex){
						currentBuild.result= 'FAILURE'
					}
					junit 'newman.xml'
				}
                
            }
        }
	}
}