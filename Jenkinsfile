pipeline {

	agent any
	stages {
	  stage('build') {
		steps {
		  sh 'mvn install -DskipTests'
		}
	  }

	  stage('test') {
		  steps {
				sh 'echo a'
			}
		 post {
			 always{
				archiveArtifacts artifacts: 'target/**.jar', followSymlinks: false
				junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
			 }
			}
	  }

}

}
