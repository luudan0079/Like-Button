pipeline {
    agent any

    stages {

        stage('Compile stage') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test stage') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Cucumber report') {
            steps {
                echo 'Example 1'
                cucumber fileIncludePattern: '**/cucumber-report.json', sortingMethod: 'ALPHABETICAL'
            }
        }
        stage('Example 2') {
            steps {
                echo 'Example 2'
            }
        }
    }
    post {
        always {
            echo 'One way or another, I have finished'
            deleteDir() /* clean up our workspace */
        }
        success {
            echo 'success'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}