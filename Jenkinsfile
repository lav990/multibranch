pipeline {
    agent {label 'agent'}

    stages {
        stage ('checkout') {
            steps {
               echo "Running on branch: ${env.BRANCH_NAME}"
            }
        }

        stage ('unit tests') {
            steps {
                sh 'echo Running unit tests'
            }
        }

        stage ('trivy scan') {
            steps {
                sh 'echo Running trivy scan'
            }
        }

        stage ('build') {
            when {branch 'main'}
            steps {
                sh 'echo mvn clean package'
            }
        }

        stage ('deploy') {
            when {branch 'main'}
            steps {
                 sh 'echo java -jar app.jar'
            }
        }
    }
}
