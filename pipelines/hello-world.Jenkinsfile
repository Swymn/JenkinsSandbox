pipeline {
    agent any

    parameters {
        string(name: 'branch', defaultValue: 'main', description: 'Branch to build')
    }

    triggers {
        cron('0 3 * * 1-5')
    }

    environment {
        SENTENCE = 'I hope your borther\'s El Camino runs forever'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build the project...'
            }
        }
        stage('Package') {
            when {
                expression {
                    return params.branch == 'release'
                }
            }
            steps {
                echo 'Packing the code...'
            }
        }
    }
}