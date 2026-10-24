@Library('Shared')_
pipeline {
    agent { label 'dev-server' }

    triggers {
        githubPush()
    }

    stages {
        stage("Code clone") {
            steps {
                sh "whoami"
                clone("https://github.com/itsmedaksh3048-blip/Django_Notes_App.git", "main")
            }
        }
        stage("Code Build") {
            steps {
                dockerbuild("notes-app", "latest")
            }
        }
        stage("Push to DockerHub") {
            steps {
                dockerpush("dockerHubCreds", "notes-app", "latest")
            }
        }
        stage("Deploy") {
            steps {
                deploy()
            }
        }
    }

    post {
        success {
            echo "Build and deploy succeeded"
        }
        failure {
            echo "Build failed, check the stage logs above"
        }
    }
}
