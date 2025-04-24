pipeline {
    agent any     
    stages {         
        stage('Checkout') {             
            steps {                 
                git branch: 'master', url: 'https://github.com/JohnnyChuan2006/hello-world-java1.git'             
            }         
        }         
        stage('Build') {             
            steps { bat 'gradle build'}         
        }         
        stage('Test') {             
            steps { bat 'gradle test'}         
        }         
        stage('Deploy') {             
            steps { bat 'java -jar build/libs/hello-world-javaV1.jar'}                    
        }     
    }

    post { 
        always { 
            echo 'Cleaning up workspace' 
            deleteDir() // Clean up the workspace after the build 
        } 
        success { 
            echo 'Build succeeded!!!' // You could add notification steps here 
        } 
        failure { 
            echo 'Build failed!' // You could add notification steps here 
        } 
    } 
}