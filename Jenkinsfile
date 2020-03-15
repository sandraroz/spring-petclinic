pipeline {
    agent any


    stages {
        stage('Build') {
            steps {
                bat './mvnw build' 
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
                echo 'Pretend to deploy'
               // bat './mvnw deploy' 
            }            
        }
    }
}
