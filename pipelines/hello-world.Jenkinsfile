pipeline {
    agent any

    triggers {
        cron('0 3 * * 1-5')
    }

    environment {
        SENTENCE = 'I hope your borther\'s El Camino runs forever'
    }

    stages {
        stage('SCM Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Swymn/JenkinsSandbox.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Build the project...'
            }
        }
    }
}