node {

 checkout([$class: 'GitSCM', branches: [[name: '*/Test']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/KiranSonawane2003/time-tracker.git']]])
sh 'mvn -B -V -U -e clean package'
 junit '**/target/surefire-reports/TEST-*.xml'
 archiveArtifacts '**/target/*.jar'

  
  }
