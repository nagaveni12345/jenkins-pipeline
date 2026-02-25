pipeline {
    agent any

    environment {
        TOMCAT_WEBAPPS = "/var/lib/tomcat9/webapps"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                    git url: 'https://github.com/nagaveni12345/jenkins-pipeline.git', branch: 'master'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh '''
                echo "Removing old deployment..."
                sudo rm -rf $TOMCAT_WEBAPPS/frontend-app*

                echo "Copying WAR file..."
                sudo cp target/frontend-app.war $TOMCAT_WEBAPPS/
                '''
            }
        }

        stage('Success') {
            steps {
                echo "Deployment Successful!"
            }
        }
    }
}
