pipeline{
    agent any
    triggers{
        githubPush()
    }
    stages{
       stage('Checkout'){
           steps{
               git branch: 'main', url: 'https://github.com/NamanUM/repo1.git'
           }
       }
       stage('Build'){
           steps{
               sh 'npm install'
           }
       }
       stage('Test'){
           steps{
               sh 'npm test'
           }
       }
       stage('Deploy'){
           steps{
               sh './deploy.sh'
           }
       }
    }
}
