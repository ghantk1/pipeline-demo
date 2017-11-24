pipeline {
  agent any
  stages {
    stage('Prepare Integration Enviroment') {
      steps {
        echo 'Integration Env'
      }
    }
    stage('Deploy from Master Branch') {
      steps {
        echo 'Master'
      }
    }
    stage('Deploy Single System Def.') {
      steps {
        echo 'System Def'
      }
    }
    stage('System Integration tests') {
      steps {
        echo 'System Integration Tests'
      }
    }
    stage('Update Dashboards') {
      steps {
        parallel(
          "Update Dashboards": {
            echo 'Dashboard'
            
          },
          "Generate Reports": {
            echo 'Report Generation'
            
          },
          "Notify Errors": {
            echo 'Error'
            
          }
        )
      }
    }
  }
}