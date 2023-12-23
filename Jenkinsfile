pipeline {
    agent any
    triggers {
        cron('H */4 * * 1-5')
    }

    stages {
        stage('Set up env') {
            steps {
                script {
                    sh 'python3 -m pip install --upgrade pip'
                    sh 'pip3 install -r requirements.txt'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh 'python3 -m pytest ./test_api/test_api_login.py'
                }
            }
        }
    }
}
