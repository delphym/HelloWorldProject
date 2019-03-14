pipeline {
  agent any
  stages {
    stage('Initialalize') {
      steps {
        echo 'This is my minimal pipeline'
        sh '''if [ "$(ls -A FW)" ]; then
     rm FW/*
fi

./mcs_buildall.sh mcspuck

./mcs_buildall.sh mcsangelo

./mcs_buildall.sh mcsotira
'''
      }
    }
    stage('Build') {
      steps {
        echo 'Run another shell script'
      }
    }
    stage('Archive') {
      steps {
        archiveArtifacts './target/**/*.jar ./target/**/*.hpi'
      }
    }
  }
}