pipeline {
    agent {
        docker {
            image 'python:3.10'
        }
    }

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest -n 4 --alluredir=allure-results'
            }
        }

        stage('Generate Report') {
            steps {
                sh 'allure generate allure-results -o allure-report --clean'
            }
        }
    }
}
