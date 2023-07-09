pipeline {
     agent any
     stages {
         stage('build') {
             steps {
                echo 'Building..'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'rachellerathbone.atlassian.net'
                 }
             }
         }
        stage('test') {
            steps {
                echo 'Testing..'
            }
            post {
                 always {
                     jiraSendBuildInfo site: 'rachellerathbone.atlassian.net'
                 }
             }
        }
        stage('deployments') {
            parallel {
                stage('deploy to stg') {
                    steps {
                        echo 'stg deployment done'
                    }
                }
                stage('deploy to prod') {
                    steps {
                        echo 'prod deployment done'
                    }
                }
            }
            post {
                 always {
                     jiraSendBuildInfo site: 'rachellerathbone.atlassian.net'
                 }
             }
        }
     }
 }
