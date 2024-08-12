pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/sivasankars1990/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with siva'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with siva'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with siva'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with siva'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t sivasankars1990/project:3 .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8085-8085 --name c005 myimg'
            }
        }   
    }
}
