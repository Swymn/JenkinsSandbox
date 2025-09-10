pipeline {
    agent any

    parameters {
        string(name: 'branch', defaultValue: 'main', description: 'Branch to build')
    }

    stages {
       stage('Parallel Phases'){
           parallel{
               stage('Static Analysis'){
                   steps {
                       echo 'perform static analysis'
                       sleep time: 3, unit: 'SECONDS'
                       echo 'sa complete'
                   }
               }
               stage('Build and Test'){
                   stages{
                       stage('Build') {
                           steps {
                               echo 'build the code'
                               sleep time: 3, unit: 'SECONDS'
                               echo 'build complete'
                               // build the code
                           }
                       }
                       stage('Unit Test'){
                           steps{
                               echo 'execute unit tests'
                               sleep time: 3, unit: 'SECONDS'
                               echo 'unit tests complete'
                           }
                       }
                   }
               }
           }
       }
       stage('Package') {
           steps {
               echo 'Packaging the code for release'
           }
       }
    }
}