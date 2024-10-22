pipeline {
    agent {
        label 'agent'
    }
    environment {
        PYTHON_ENV = "${WORKSPACE}/venv"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/SeNike/ansible-vector', branch: 'main'
            }
        }
        stage('Setup Python Environment') {
            steps {
                script {
                    sh 'python3 -m venv ${PYTHON_ENV}'
                    sh '. ${PYTHON_ENV}/bin/activate && pip install --upgrade pip'
                    sh '. ${PYTHON_ENV}/bin/activate && pip install molecule molecule_docker molecule_podman ansible'
                }
            }
        }
        stage('Run Molecule Test') {
            steps {
                script {
                    sh '. ${PYTHON_ENV}/bin/activate && molecule test'
                }
            }
        }
    }
    post {
        always {
            deleteDir()
        }
        success {
            echo 'Molecule tests passed successfully!'
        }
        failure {
            echo 'Molecule tests failed.'
        }
    }
}
