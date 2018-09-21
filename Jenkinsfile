node {

 
  stage('Checkout') {
    git 'https://github.com/KiranSonawane2003/time-tracker.git'
  }

 stage('Build') {
    sh 'mvn -B -V -U -e clean package'
  }

  stage('Archive') {
    archiveArtifacts '**/target/*.jar'

   //junit allowEmptyResults: true, testResults: '**/target/**/TEST*.xml'
  }
 

 
 
 stage('PMD') {

  //line written bellow works perfect. I forgot to install pmd plugins.
    step([$class: 'hudson.plugins.checkstyle.CheckStylePublisher', checkstyle: '**/target/checkstyle-result.xml'])
      step([$class: 'hudson.plugins.pmd.PmdPublisher', checkstyle: '**/target/pmd.xml'])
 
  
  step([$class: 'CheckStylePublisher',
                      canRunOnFailed: true,
                      defaultEncoding: '',
                      healthy: '100',
                      pattern: '**/target/checkstyle-result.xml',
                      unHealthy: '10',
                      useStableBuildAsReference: true
                    ])

}

 
}
