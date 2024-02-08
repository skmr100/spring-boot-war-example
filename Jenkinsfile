pipeline {
    agent any

    tools{
        maven 'Maven'
    }

    stages {
        stage('Test') {
            steps {
                echo 'Package Testing'
                //mvn test
                sh "mvn test"
            } 
        }    
        stage('Build') {
            steps {
                echo 'Builing Project'
                //mvn install
                sh "mvn package"
            }
        }
        // stage('Deploy to Test') {
        //     steps {
        //         echo 'Deploying to Test'
        //         deploy adapters: [tomcat9(credentialsId: 'sanjay', path: '', url: 'http://52.66.244.238:8080/')], contextPath: '/app', war: '**/*.war'

        //     }
        // }   
        // stage('Deploy to Prod') {
        //     steps {
        //         echo 'Deploying to Production'
        //         deploy adapters: [tomcat9(credentialsId: 'sanjay', path: '', url: 'http://3.108.238.102:8080/')], contextPath: '/app', war: '**/*.war'
        //     }
        // }   
        
    }
}
