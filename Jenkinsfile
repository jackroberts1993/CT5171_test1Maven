pipeline{
    agent any

    stages{
        stage('GetProject'){
            steps{
                git 'https://github.com/jackroberts1993/CT5171_test1Maven.git'
            }
        }

        stage('Build'){
            steps{
                //Run Maven on an agent on Linyx Machine with Maven installed
                sh "mvn clean:clean"
                sh "mvn dependency:copy-dependencies"
                sh "mvn compiler:compile"

                //To run Maven on a Windows agent, use bat instead of sh
                //bat "mvn clean"

            }
        }

        stage('Execute'){
            steps{
                sh "mvn exec:java"
            }
        }
    }
}