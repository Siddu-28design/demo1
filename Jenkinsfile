pipeline {

	agent { label 'Windows_Slave_Siddu' }

	
	tools {
  maven 'Maven3'
}
	
	parameters {
  string defaultValue: 'adi', name: 'name', trim: true
}
	stages {
	  stage('build') {
		steps {
		  sh 'mvn install -DskipTests'
		}
	  }

	  stage('test') {
		  steps {
				sh 'echo new'
			}
		 post {
			 always{
				archiveArtifacts artifacts: 'target/**.jar', followSymlinks: false
			
			 }
			}
	  }
		
}

}
