pipeline {
    agent any

    tools {
        maven 'M3' // Must match your Maven install name in Jenkins
        jdk 'JDK11' // Optional: adjust if using different JDK
    }

    options {
        timeout(time: 30, unit: 'MINUTES')
        buildDiscarder(logRotator(numToKeepStr: '10'))
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'GIT_BRANCH', defaultValue: 'feature-1.1', description: 'Git branch to build')
        choice(name: 'ENV', choices: ['dev', 'qa', 'prod'], description: 'Deployment environment')
        booleanParam(name: 'SKIP_TESTS', defaultValue: false, description: 'Skip unit tests')
    }

    environment {
        APP_NAME = 'sabear_customerapp'
        DOCKER_TAG = "${env.BUILD_NUMBER}"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: "${params.GIT_BRANCH}", url: 'https://github.com/betawins/sabear_simplecutomerapp.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    if (!params.SKIP_TESTS) {
                        sh 'mvn clean install'
                    } else {
                        sh 'mvn clean install -DskipTests'
                    }
                }
            }
        }

        stage('Test') {
            when {
                expression { return !params.SKIP_TESTS }
            }
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying ${APP_NAME} to ${params.ENV} environment with tag ${DOCKER_TAG}"
                // Example: docker build/push or kubectl apply scripts
            }
        }
    }

    post {
        success {
            echo 'gayas Build and Deployment Successful!'
        }
        failure {
            echo '001 Build or Deployment Failed!'
        }
    }
}
