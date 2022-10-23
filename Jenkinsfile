pipeline {

	agent {
		docker {
			image 'node:16.13.1-alpine'
			args '-p 3000:3000'
		}
	}

	stages {
		stage('npm install') {
			steps {
				echo 'npm install'
				sh 'npm install'

				echo 'run npm ci'
				sh 'npm ci'

				echo 'check node version'
				sh 'node --version'
			}
		}
		stage('unit tests') {
			steps {
				echo 'run unit test'
				sh 'npm run test -- --coverage --watchAll=false'
				echo 'run code coverage'
				cobertura autoUpdateHealth: false, autoUpdateStability: false, coberturaReportFile: '**/cobertura-coverage.xml', conditionalCoverageTargets: '70, 0, 0', failUnhealthy: false, failUnstable: false, lineCoverageTargets: '80, 40, 40', maxNumberOfBuilds: 0, methodCoverageTargets: '80, 0, 0', onlyStable: false, sourceEncoding: 'ASCII', zoomCoverageChart: false
			}
		}
	}
}
