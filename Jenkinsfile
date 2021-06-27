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
          sh 'newman run TestAPI_Jenkins.postman_collection.json -e QA.postman_environment.json'
        }
      }
    }
} 