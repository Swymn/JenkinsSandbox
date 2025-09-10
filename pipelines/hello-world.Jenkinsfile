pipeline {
    agent any

    parameters {
        string(name: 'branch', defaultValue: 'main', description: 'Branch to build')
    }

    environment {
        SENTENCE = 'I hope your borther\'s El Camino runs forever'
    }

    stages {
        stage('Parallel Stages') {
            parallel {
                stage('Static Analysis') {
                    steps {
                        echo 'Running static analysis...'
                        sleep time: 3, unit: 'SECONDS'
                    }
                }

                stage('Build and test') {
                    stages {
                        stage('Build') {
                            steps {
                                echo 'Build the project...'
                                sleep time: 3, unit: 'SECONDS'
                            }
                        }

                        stage('Unit Testing') {
                            steps {
                                echo 'Testing the project...'
                                sleep time: 3, unit: 'SECONDS'
                            }
                        }
                    }
                }
            }

            stage('Package') {
                steps {
                    echo 'Packing the code...'
                    sleep time: 3, unit: 'SECONDS'
                }
            }
        }
    }
}