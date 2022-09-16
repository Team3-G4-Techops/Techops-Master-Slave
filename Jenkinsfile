pipeline{
  agent {
    label {
      label 'slave1'
    }
  }
  stages{
    stage('git-clone - Sithabile'){
        steps{
            checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/Team3-G4-Techops/Techops-Master-Slave.git']]])
        }
    }
    stage('parallel-job 1'){
      parallel{
        stage('sub-job1 - Sithabile'){
          steps{
            sh 'echo master slave test'
          }
        }
        stage('sub-job 2 - roger'){
          steps{
            sh 'echo master slave test'
          }
        }
      }
    }
     stage('parallel-job 2'){
      parallel{
        stage('sub-job1 - Roger'){
          agent {
            label {
              label 'slave2'
            }
          }
          steps{
            sh 'ps -ef'
          }
        }
          stage('sub-job2 - Kingue'){
            agent {
              label {
                label 'slave3'
              }
            }
           steps{
            sh 'ps -ef'
          }
        }
      }
    }
    stage('parallel-job 3'){
      parallel{
        stage('sub-job1 - Constance'){
          steps{
            sh 'ps -ef'
          }
        }
        stage('sub-job2 - Wille'){
          agent {
            label {
              label 'slave2'
            }
          }
          steps{
            sh 'ps -ef'
          }
        }
      }
    }
  }
}
