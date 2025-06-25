pipeline{
    agent any
    stages{
      stage('Checkout'){
        git branch: 'main',url: 'https://github.com/dai08/ml-pipeline.git'
      } 

    }  
    stage('install Dependencies'){
      steps{
        sh "pip install -r requirements.txt"
      }
    }
    stage('Train Model'){
      steps{
        sh 'python3 train.py'
      }
    }
    stage('Archive Model'){
      steps{
        archiveArtifacts artifacts: 'model.pkl', fingerprint:true
      }
    }
  }
}
