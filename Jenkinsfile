parameters {
    booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
}
pipeline {
    agent any
    environment {
    MY_VERSION = '1.0.0'
}
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "Version: ${env.MY_VERSION}"
            }
        }
        stage('Test') {
            when {
                expression { return params.executeTests == true }
            }
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
   post {
        always {
            echo 'Build complete!'
        }
    }
}
