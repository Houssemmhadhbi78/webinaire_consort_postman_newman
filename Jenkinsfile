pipeline {
    agent any
    tools {nodejs "nodejs"}
    
    stages {
      
      stage("Newman package installation") {
        steps {
          sh 'npm install -g newman'
        }
      }
      stage("Run newman") {
        steps {
          sh 'newman run "Newman Avec IterableData.json" -e Prod.json -d iterationData.json'
        }
      }
    }
}