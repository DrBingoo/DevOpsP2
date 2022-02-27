pipeline {
    agent any
    tools{
      maven 'maven 3.8.2'
      jdk 'JDK 1.8'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                bat 'mvn -f HelloWorldJavaEE/pom.xml clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                bat 'mvn -f HelloWorldJavaEE/pom.xml test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post{
      always{
        emailext body: 'Jenkins devops-pipeline is run', subject: 'Jenkins Pipeline', to: '2002393C@student.tp.edu.sg'
      }
    }
}
