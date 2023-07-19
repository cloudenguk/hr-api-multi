pipeline{
    agent any
    stages{
        stage('Git Checkout'){
            steps{
                git url:"https://github.com/cloudenguk/hr-api-multi", branch: "main"
            }
        }
        stage('Maven Build'){
            steps{
                sh "mvn clean package"
            }
        }
        stage('Dev Deploy'){
            when{
                branch 'develop'
            }
            steps{
                echo "deploying to dev environment"
            }
        }
        stage('QA Deploy'){
            when{
                branch 'qa'
            }
            steps{
                echo "deploying to qa environment"
            }
        }
        stage('Prod Deploy'){
            when{
                branch 'main'
                
            }
            steps{
                echo "deploying to production environment"
            }
        }
}