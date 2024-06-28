pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/gotoa1234/GitFlowTemplate.git'
                
                sh """
                   git checkout ${params.GIT_HASH}
                """
            }
        }

        stage('Building') {
            steps {
                 script {
                    sh """
                    dotnet build GitFlowWebSiteExample/GitFlowWebSiteExample.csproj -c Release -o GitFlowWebSiteExample/publish/GitFlowWebSiteExamplePackage
                    """
                }
            }
        }

        stage('Test') {
            steps {
                // 測試命令 - 假裝自動化測試
                echo "Running tests... (Mock)"
            }
        }
    }

    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}
