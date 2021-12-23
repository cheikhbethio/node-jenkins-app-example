pipeline {
  agent any
    
  tools {nodejs "node 16"}
    
  stages {

    stage('Git') {
      steps {
        git([
            url: 'https://github.com/cheikhbethio/node-jenkins-app-example.git', 
            branch: '**',
            credentialsId: 'a1641d36-10de-4cdf-9f52-268fb996e301'
            ])
      }
    }
     
    stage('install deps') {
      steps {
        sh 'npm install'
      }
    }  
    
            
    stage('Test') {
      steps {
        sh './script/test'
      }
    }
    
            
    stage('deploy') {
      steps {
        sh 'pwd && ls'
        sh 'cat ./script/build'
        sh './script/build'
      }
    }
  }
}