pipeline {
    agent any 
    environment{
        PATH ="\WINDOWS\system32\config\systemprofile\AppData\Local\Jenkins\.jenkins\workspace"
    }
   
    stages {
        stage('Build') {
            steps {
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') { 
            steps {
                bat 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
    }
}
