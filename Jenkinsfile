pipeline{
  agent any
  stages{
    stage("Bulid"){
      steps{
          echo 'building the project'
    }
     stage("test"){
       steps{
          echo 'testing the project '
       }
    }
       stage ('Check-Git-Secrets') {
      steps {
        sh 'rm trufflehog || true'
        sh 'docker run gesellix/trufflehog --json https://github.com/cehkunal/webapp.git > trufflehog'
        sh 'cat trufflehog'
      }
    }
     stage("deploy"){
       steps{
          echo 'deploying the project '
       }
    }
  }
}
