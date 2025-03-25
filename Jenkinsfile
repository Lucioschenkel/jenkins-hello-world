pipeline {
    agent any
    
    tools {
        // Install the maven version configured as "M398" and add it to path
        maven "M398"
    }
    
    stages {
        stage('Echo version') {
            steps {
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }
        
        stage('Build') {
            steps {
                // Get the code from Gitea repository
                // Not needed if Jenkins is already configured to pull this Jenkinsfile from the repo
                // git branch: 'main', changelog: false, poll: false, url: 'http://gitea:3000/Dashr/jenkins-hello-world.git'
                
                // Run maven package command
                sh 'mvn clean package -DskipTests=true'   
            }
        }
        
        stage('Unit Test') {
            steps {
                sh "mvn test"
            }
        }
    }
}