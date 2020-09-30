pipeline {
    agent any
    options {
        buildDiscarder(logRotator(daysToKeepStr:'1', numToKeepStr:'2'))
    }
    stages{
        stage("checkout scm"){
            steps{
                echo "COde is checkedout"
            }
        }
        stage("BUILD"){
            steps {
                echo "BUILD"
                sh 'mvn clean compile'
            }

        }

        stage("Test"){
            steps{
                sh 'mvn test'
            }
        }
        stage("Jacoco"){
            steps {
                echo "Code Coverage"
                jacoco()
            }
        }
        stage("Package"):
        {
            steps{
                sh 'mvn package -DskipTests'
            }
        }
        
    }


}