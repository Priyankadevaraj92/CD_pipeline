pipeline {
    agent any
    
    environment {
        JAVA_HOME = tool name: 'Java', type: 'jdk'
    }
    
    stages {
                
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'cp target/your-project.war $CATALINA_HOME/webapps/'
            }
        }
    }
    
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed!'
        }
    }
}
