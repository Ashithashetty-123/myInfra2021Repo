pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
    
        stage ("terraform init") {
            steps {
                bat "terraform init -reconfigure"
            }
        }
        
        stage ("plan") {
            steps {
                bat 'terraform plan'
            }
        }

        stage (" Action") {
            steps {
                echo "Terraform action is --> ${action}"
                bat 'terraform ${action} --auto-approve'
           }
        }
    }
}
    
