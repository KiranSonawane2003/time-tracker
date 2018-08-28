node {

 
  stage('Checkout') {
    git 'https://github.com/KiranSonawane2003/time-tracker.git'
  }

 stage('Build') {
    sh 'mvn clean package'
  }

  stage('Archive') {
    junit allowEmptyResults: true, testResults: '**/target/**/TEST*.xml'
  }

 
}
