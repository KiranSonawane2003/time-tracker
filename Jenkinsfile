node {

 checkout([$class: 'GitSCM', branches: [[name: '*/Test']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/KiranSonawane2003/time-tracker.git']]])
def mvnHome = tool 'M3'
  sh "${mvnHome}/bin/mvn -B -Dmaven.test.failure.ignore verify"
 junit '**/target/surefire-reports/TEST-*.xml'
 archiveArtifacts '**/target/*.jar'

  
  }
