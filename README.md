https://medium.com/@mosheezderman/how-to-set-up-ci-cd-pipeline-for-a-node-js-app-with-jenkins-c51581cc783c


Deployer une appi node js depuis git par jenkins
jenkins est en local
le deploiement se fait sur ma machine
on utilise ngRok pour creer des liens public vers ma machine (ce ci est indispensable car les webhook exigent des des url public et non des localhots)

create project with pipepline

GitHub hook trigger for GITScm polling

pipeline {
  agent any
    
  tools {nodejs "node 16"}
    
  stages {
        
    stage('Git') {
      steps {
        git([
            url: 'https://github.com/cheikhbethio/node-jenkins-app-example.git', 
            branch: 'node-pipeline-script',
            credentialsId: 'added from credentials'
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
        sh './script/deploy'
      }
    }
  }
}