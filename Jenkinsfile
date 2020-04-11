pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
          steps {
                withAWS(region:'es-east-2',credentials:'aws-static') {
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'udacity-jenkins-project-3')
                }
           }
        }
    }
}