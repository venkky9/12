pipeline {
  agent {
    docker {
      image 'jenkinsmaven:latest'
    }
  }

  stages {
    stage('SCM') {
        steps {
      		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/executeautomation/SeleniumWithCucucumber']]])
	      }
    }

    stage('Build') {
          steps {
               sh 'mvn compile'
          }
    }

    stage('Publish') {
          steps {
    	      sh 'mvn test'
          }
    }
  }
}
