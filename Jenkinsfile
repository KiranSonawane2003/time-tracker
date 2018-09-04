node {

 
  stage('Checkout') {
    git 'https://github.com/KiranSonawane2003/time-tracker.git'
  }

 stage('Build') {
    sh 'mvn -B -V -U -e clean package'
  }

  stage('Archive') {
    junit allowEmptyResults: true, testResults: '**/target/**/TEST*.xml'
  }
 
 stage('CAT') {

   // step([$class: 'hudson.plugins.checkstyle.CheckStylePublisher', checkstyle: '**/target/checkstyle-result.xml'])

    step([$class: 'hudson.plugins.pmd.PmdPublisher', checkstyle: '**/target/pmd.xml'])

}

 
}
