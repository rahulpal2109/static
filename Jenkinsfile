pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                withAWS(region:'ap-south-1', credentials:'aws-static') {
                    s3Upload(file:'index.html', bucket:'udacity-pal-devops', path:'/index.html')
                }
            }
        }
    }
}
