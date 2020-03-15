pipeline {
    agent any


    stages {
        stage('Build') {
            steps {
                bat './mvnw install' 
            }
        }

        stage('Test') {
            steps {
                bat './mvnw test' 
            }
        }

        stage('Package') {
            steps {
                bat './mvnw package' 
            }
        }

        stage('Deploy') {
            when {
                expression { env.BRANCH_NAME == 'master'}
            }          
            steps {
                bat './mvnw package' 
            }            
        }
    }
}
