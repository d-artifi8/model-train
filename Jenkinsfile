pipeline {
    agent any
    stages { // This 'stages' block encloses all individual 'stage' blocks
        stage('Checkout') {
            steps { // 'steps' block is required inside a stage
                git branch: 'main', url: 'https://github.com/dai08/ml-pipeline.git'
            }
        }
        stage('Install Dependencies') { // Corrected indentation and placed inside 'stages'
            steps {
                sh "pip install -r requirements.txt"
            }
        }
        stage('Train Model') { // Corrected indentation and placed inside 'stages'
            steps {
                sh 'python3 train.py'
            }
        }
        stage('Archive Model') { // Corrected indentation and placed inside 'stages'
            steps {
                archiveArtifacts artifacts: 'model.pkl', fingerprint: true
            }
        }
    } // End of 'stages' block
}
