pipeline {
    
  agent any
  
  stages {
        
    stage('Cloning Git') {
      steps {
        git branch: 'main', credentialsId: 'Github', url: 'https://github.com/pdrodavi/node-jenkins-heroku.git'
      }
    }
        
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
    
    stage('Cloning Git Heroku') {
      steps {
        git credentialsId: '1b1edcd5-554f-41b1-b20e-a7b096515600', url: 'https://git.heroku.com/node-jenkins-heroku.git'
      }
    }
    
    stage('Deploy') {
        steps {
            sh 'git add .'
            sh 'git commit -am "up"'
            sh 'git push https://heroku:abac6b25-8275-4d13-89b5-531b95f80790@git.heroku.com/node-jenkins-heroku.git HEAD:refs/heads/master'
        }
    }
         
  }
}
