pipeline {
    agent any

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
