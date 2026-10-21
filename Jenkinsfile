pipeline {
    agent any

    stages {
        stage('Get Source Code from Github Repository') {
            steps {
                git branch: 'main', 
                url: 'https://github.com/RLNarasimham/pet_shop.git'
            }
        }
        stage('Build Application/Software using Apache Maven'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Deploy Application/Software using Apache Tomcat'){
            steps{
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'PET_SHOP_COMP_PIPELINE_CREDS', path: '', url: 'http://40.192.58.152:8090/')], contextPath: 'pet_shop_app', war: '**/*.war'
            }
        }
    }
}
