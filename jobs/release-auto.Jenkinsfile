// Release of maven version by taking the input from User

pipeline {
  agent { 
    node {
      label 'MAVEN'
    }
  }
  environment {
    NEXUS=credentials('Nexus-Cred')
    GIT=credentials('GitUserPass')
  }
  stages {

    stage('Clone the Repo') {
      steps {
        git credentialsId: 'GitUserPass', url: 'https://github.com/AnoopKumar39/studentapp-ui.git'
      }
    }

    stage('Upload Artifacts') {
      steps {
        sh '''
          mvn -s settings.xml release:prepare -Dresume=false --batch-mode -DGIT_USR=${GIT_USR} -DGIT_PSW=${GIT_PSW} -DNEXUS_USR=${NEXUS_USR} -DNEXUS_PSW=${NEXUS_PSW}
          mvn -s settings.xml release:perform -DGIT_USR=${GIT_USR} -DGIT_PSW=${GIT_PSW} -DNEXUS_USR=${NEXUS_USR} -DNEXUS_PSW=${NEXUS_PSW}
        '''
      }
    } 
}
}
