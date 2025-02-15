pipeline {
    agent any

     environment {
        GIT_REPO = '' // Update withttps://github.com/manasaa15/FlaskJenkinsAPP.gith your repo
        PATH = "C:\\Windows\\System32;C:\\Program Files\\Git\\bin;"
    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/manasaa15/FlaskJenkinsAPP.git'
                }
            }
        }

        stage('Set up Python Virtual Environment') {
            steps {
                script {
                    bat 'python -m venv venv'
                    bat 'venv\\Scripts\\activate && pip install -r requirements.txt'
                }
            }
        }

        stage('Run Flask Application') {
            steps {
                script {
                    bat 'venv\\Scripts\\activate && python app.py'
                }
            }
        }
    }
}
