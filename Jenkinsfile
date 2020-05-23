pipeline {
    agent any

    stages {
        stage('Lint HTML') {
            steps {
                tidy -q -e *.html
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(region:'ap-south-1', credentials:'aws-static') {
                    s3Upload(file:'index.html', bucket:'udacity-pal-devops', path:'index.html')
                }
            }
        }
    }
}
