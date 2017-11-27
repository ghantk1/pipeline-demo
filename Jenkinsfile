pipeline {
  agent any
  stages {
    stage('System Test Environment') {
      steps {
        echo 'Integration Env'
      }
    }
    stage('Deploy from Master Branch') {
      parallel {
        stage('Deploy from Master Branches') {
          steps {
            echo 'Master'
          }
        }
        stage('Artifacts download from Snapshot location') {
          steps {
            echo 'snapshot'
          }
        }
      }
    }
    stage('Deploy Single System Def.') {
      steps {
        echo 'System Def'
      }
    }
    stage('Run System Level Testing') {
      steps {
        echo 'System Integration Tests'
      }
    }
    stage('Update Dashboards') {
      parallel {
        stage('Update Dashboards') {
          steps {
            echo 'Dashboard'
          }
        }
        stage('Generate Reports') {
          steps {
            echo 'Report Generation'
          }
        }
        stage('Notify Errors') {
          steps {
            echo 'Error'
          }
        }
      }
    }
    stage('Release') {
      parallel {
        stage('Github Release tag') {
          steps {
            echo 'Release'
          }
        }
        stage('Maven release prepare') {
          steps {
            echo 'Prepare'
          }
        }
        stage('Maven release perform') {
          steps {
            echo 'Perform'
          }
        }
      }
    }
    stage('Release stable branch') {
      steps {
        echo 'Stable'
      }
    }
    stage('Maven Release deploy') {
      steps {
        echo 'Maven Central'
      }
    }
  }
}