@Library("shaed") _
pipeline {
    agent { label 'Daksh' }
    stages {
        stage("hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage('Clean old data') {
            steps {
                sh 'docker compose down --remove-orphans || true'
                sh 'sudo rm -rf data || true'
            }
        }
        stage('Code clone') {
            steps {
                script{
                    clone("https://github.com/itsmedaksh3048-blip/Django-Notes-App.git","main")
                }
            }
        }
        stage('Code Build') {
            steps {
                script{
                    build("notes-app","latest","itsmedaksh3048")
                }
            }
        }
        stage('Push to DockerHub') {
            steps {
                script{
                    push("notes-app","latest","itsmedaksh3048") 
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker compose down --remove-orphans || true'
                sh 'docker compose up --build -d'
            }
        }
    }
}
