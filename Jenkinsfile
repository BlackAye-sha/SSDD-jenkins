parameters {
    booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
}
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
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
