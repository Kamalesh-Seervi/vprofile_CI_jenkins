pipeline {
    agent any
    tools {
	    maven "MAVEN"
	    jdk "aws_jdk"
	}

    stages{
        stage('Fetch code') {
          steps{
              git branch: 'checkstyle', url:'https://github.com/Kamalesh-Seervi/vprofile_CI_jenkins.git'
          }  
        }

        stage('Build') {a
            steps {
                sh 'mvn clean install -DskipTests'
            }
            post {
                success {
                    echo "Now Archiving."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('Test'){
            steps {
                sh 'mvn test'
            }

        }

        stage('Checkstyle Analysis'){
            steps {
                sh 'mvn checkstyle:checkstyle'
            }
        }

    }
}