pipeline {
    agents any
    stages {
        stage('Clone Repo'){
            steps {
                git branch: 'main', url: 'https//github.com/NamanUM/repo1.git'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install' 
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                sh './deploy.sh to staging'
            }
        }
        stage('production') {
            when {
                branch 'main'
            }
            steps {
                sh './deploy.sh to prod'
            }
        }
    }
    post {
        always {
            echo "Pipeline execution \$\$"
        }
    }
}
