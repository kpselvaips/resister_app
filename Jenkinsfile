pipeline {
  agent { label 'jenkins_agent'}
  tools {
    jdk 'java17'
    maven 'maven3'
  }
  stages {
    stage ("Cleanup Worksapce") {
      steps {
        cleanWs()
      }
    }
    stage ( "checkout from SCM") {
      steps {
        git branch: 'main', credentialsId:'github', url : 'https://github.com/kpselvaips/resister_app'
      }
    }
    stage("Build Application"){
      steps {
        sh "mvn clean package"
      }
    }
    stage("Test Application"){
      steps {
        sh "mvn test"
      }
    }
  }
}
