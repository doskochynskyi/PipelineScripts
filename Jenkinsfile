pipeline {
    agent any
    stages {
        stage('Git checkout') {
            steps {
                echo "Get from Git"
                
            }    
        }
        stage('Compile') {
            steps {
                echo "Compile successfully"
                bat 'Build.bat'
            }    
        }
        stage('JUnit') {
            steps {
                echo "JUnit passed successfully"
                bat 'Unit.bat'
            }    
        }
        stage('Quality-Gate') {
            steps {
                echo "SonarQube Quality Gate passed successfully"
                bat 'Quality.bat'
            }    
        }
        stage('Deploy') {
            steps {
                echo "Deploy successfully"
                bat 'Deploy.bat'
            }    
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successfull'
        }
        failure {
            echo 'This will run if failed'
        }
        unstable {
            echo 'This will run only if the ran was marked as unstable'
        }
        changed {
            echo 'This will run if state of previous run changed'
        }
    }
}
