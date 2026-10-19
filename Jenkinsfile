pipeline {
    agent any

    stages {
        stage('Source Code Pull Stage') {
            steps {
                git branch: 'main', 
                url: 'https://github.com/RLNarasimham/pet_shop.git'
            }
        }
        
        stage('Create Build with Maven Stage'){
            steps{
                sh 'mvn clean package'
            }
        }
    }
}
