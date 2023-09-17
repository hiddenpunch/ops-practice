pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/hiddenpunch/ops-practice.git will replace by sed command before RUN
        git url: 'https://github.com/hiddenpunch/ops-practice.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}