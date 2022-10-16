pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }
       
        stage('publish to nexus'){
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.8-SNAPSHOT.war', type: 'war']], credentialsId: '46aa57c7-c79a-40ab-8bfc-f97cec27675b', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.24:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'DevOpsLabs-SNAPSHOT', version: '0.0.8'
            }
        }

        
        
    }

}