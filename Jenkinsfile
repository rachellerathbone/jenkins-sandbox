pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                echo 'Building..'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'rachellerathbone.atlassian.net'
                 }
             }
         }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
            post {
                 always {
                     jiraSendBuildInfo site: 'rachellerathbone.atlassian.net'
                 }
             }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
            post {
                 always {
                     jiraSendBuildInfo site: 'rachellerathbone.atlassian.net'
                 }
             }
        }
     }
 }
