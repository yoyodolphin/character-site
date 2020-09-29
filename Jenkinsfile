pipeline {
  agent any
  
  stages{
    stage('install') {
      steps {
        sh 'npm install'
      }
    }
    stage('test') {
      steps {
        sh 'npm run lint'
      }
    }
    stage('build') {
      steps {
        sh 'npm run build'
      }
    }
    stage('deploy') {
      steps{
        sh 'rsync -av /var/jenkins_home/workspace/characterWebSite/stage/dist/ yoyo@133.167.75.22:/var/https-portal/vhosts/yoyo-dolphin.com/'
  }
}
