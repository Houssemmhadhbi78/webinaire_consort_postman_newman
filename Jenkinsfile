pipeline {
    agent any
    tools {nodejs "nodejs"}

    stages {

      stage("Newman package installation") {
        steps {
          bat 'npm install -g newman'
        }
      }
      stage("Run newman") {
        steps {
			script {
				try {
					bat 'newman run --disable-unicode TestAPI_Datas.postman_collection.json -d recherche.csv -e QA.postman_environment.json -r cli,junit --reporter-junit-export newman.xml'
					currentBuild.result = 'SUCCESS'
				}catch (Exception ex) {
					currentBuild.result = 'FAILURE'
                }
                junit 'newman.xml'
				}
			}
		}
	}
 } 

