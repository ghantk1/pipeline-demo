pipeline {
  agent any
  stages {
    stage('Integration Environment') {
      steps {
        echo 'Integration Env'
      }
    }
    stage('Deploy from Master Branches') {
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