pipeline {
    agent any
    stages {
        state('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
          steps {
                withAWS(region:'us-east-2',credentials:'aws-static') {
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'udacity-jenkins-project-3')
                }
           }
        }
    }
}