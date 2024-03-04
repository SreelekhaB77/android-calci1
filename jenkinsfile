pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository from Git
                git branch: 'testcalci', url: 'https://github.com/SreelekhaB77/android-calci1.git'
            }
        }
        
        stage('Distribute to App Center') {
            steps {
                script {
                    // Retrieve the App Center API token credentials
                    withCredentials([string(credentialsId: 'appcentertoken1', variable: 'APP_CENTER_TOKEN')]) {
                        // Distribute to App Center
                        appCenter apiToken: env.APP_CENTER_TOKEN, appName: 'testcalci', distributionGroups: 'operations', mandatoryUpdate: false, notifyTesters: true, ownerName: 'SreelekhaB77', pathToApp: '**/*.apk'
                    }
                }
            }
        }
    }
}
