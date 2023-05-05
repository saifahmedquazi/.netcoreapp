pipeline {
    agent any
   environment {
        DOCKER_USERNAME = credentials('username')
        DOCKER_PASSWORD = credentials('password')
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/saifahmedquazi/.netcoreapp.git'
                sh 'ls -la'
            }
        }    
        stage('Build') {
            steps {
                sh 'docker build -t saifahmedquazi/dotnetcore .'
            }
        }
        stage('Docker login') {
            steps {
                    sh 'echo ${DOCKER_PASSWORD_USR} ${DOCKER_USERNAME_USR}'
                    sh 'echo ${DOCKER_PASSWORD_USR} | docker login -u ${DOCKER_USERNAME_USR} --password-stdin'
            }
        }        
        stage('Docker push') {
            steps {
                sh "docker push saifahmedquazi/dotnetcore"
            }
        }  
        stage('Run Image') {
            steps {
                script {
                    sh "docker run -itd --name dotnetcore -p 8081:5000 saifahmedquazi/dotnetcore"
                }
            }
        }
        //stage('Deploy to Kubernetes') {
            //steps {
                //script {
                  //  sh 'kubectl apply -f dotnetcore-deployment.yaml'
               // }
           // }
       // }
        stage('Clean Containers') {
            steps {
                script {
                    sh 'docker rm -f $(docker ps -aq)'
                }
            }
        }
    }
}

