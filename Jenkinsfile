pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Correct syntax: git inside steps block
                git url: 'https://github.com/nagaveni12345/jenkins-pipeline.git', branch: 'master'
            }
        }
        stage('Build WAR') {
            steps {
                echo 'Building WAR...'
                // your build commands here
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                echo 'Deploying to Tomcat...'
                // your deploy commands here
            }
        }
    }
}
