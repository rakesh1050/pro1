pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/rakesh1050/pro1/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with rakesh'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with rakesh'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with rakesh'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with rakesh'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c001 myimg'
            }
        }   
    }
}
