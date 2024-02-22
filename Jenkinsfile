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
        // stage('Install trivy') {
        //     steps {
        //         echo 'Installing trivy'
        //         //mvn install
        //         sh '''sudo apt-get install wget apt-transport-https gnupg lsb-release -y\
        //         wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | sudo apt-key add -\
        //         echo deb https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main | sudo tee -a /etc/apt/sources.list.d/trivy.list \
        //         sudo apt update \
        //         sudo apt install trivy -y '''
        //         }
        // }

        stage('trivy result') {
            steps {
                echo 'trivy scanning'
                //mvn install
                sh "trivy fs . > trivyreport.json"
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
