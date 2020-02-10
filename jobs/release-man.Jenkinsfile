// Release of maven version by taking the input from User

pipeline {
  agent { 
    node {
      label 'MAVEN'
    }
  }
  environment {
    NEXUS=credentials('Nexus-Cred')
  }
  stages {

    stage('Clone the Repo') {
      steps {
        git credentialsId: 'GitUserPass', url: 'https://github.com/AnoopKumar39/studentapp-ui.git'
      }
    }

    stage('Update Maven Version') {
      steps {
        sh '''
          mvn versions:set -DnewVersion=${RELEASE_VERSION}-RELEASE
          echo ${RELEASE_VERSION}
        '''
      }
    }


    // stage('Upload Artifacts') {
    //   steps {
    //     sh '''
    //       mvn clean package
    //       mvn -s settings.xml deploy -DNEXUS_USR=${NEXUS_USR} -DNEXUS_PSW=${NEXUS_PSW}
    //     '''
    //   }
    // } 
  }
}