pipeline{

	agent{
	      label 'master'
	}
	  
	environment {
	      MAJOR_VERSION=1
  	}

	stages{

		stage('Unit Test'){
			steps{
				sh 'ant -f test.xml -v'
				junit 'reports/result.xml'
			}
		}

		stage('Build'){
			steps{
				sh 'ant -f build.xml -v'
			}
		}
	}
	
	post{
		
	     always{
		    archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
	     }
	}
}

