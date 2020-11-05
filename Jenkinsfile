pipeline {
  agent any
 
  options {
    copyArtifactPermission(projectNames: 'ironic*')
  }

  stages {
    stage('package') {
      steps {
        dir('dist') {
          deleteDir()
        }
        sh 'python setup.py sdist'
        sh 'find dist -type f -exec cp {} dist/ironic.tar.gz \\;'
        archiveArtifacts(artifacts: 'dist/ironic.tar.gz', onlyIfSuccessful: true)
      }
    }
  }
}

