pipeline {
     agent any
     stages {
         stage('build') {
             steps {
                echo 'Building..'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'rachellerathbone.atlassian.net', branch: 'TEST-381-awesome-feature'
                 }
             }
         }
         stage('deploy to stg') {
             steps {
                 echo 'Deploying to Staging from...'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'us-stg-1', environmentName: 'us-stg-1', environmentType: 'staging'
                 }
             }
         }
         stage('deploy to prod') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to Production from main...'
            }
            post {
                throw new Error('help!')
                always {
                    jiraSendDeploymentInfo environmentId: 'us-prod-1', environmentName: 'us-prod-1', environmentType: 'production'
                }
            }
         }
     }
 }
