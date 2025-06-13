parameters {
    booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests?')
}
pipeline {
    agent any
    tools {
    maven 'Maven 3.8.1' // Name must match your Jenkins config
}

    environment {
    MY_VERSION = '1.0.0'
}
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "Version: ${env.MY_VERSION}"
                bat 'mvn install'
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
