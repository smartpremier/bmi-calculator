pipeline {

	agent {
		docker {
			image 'node:16.13.1-alpine'
			args '-p 3000:3000'
		}
	}

	stages {
		stage('Build') {
			steps {
				echo 'install npm'
				sh 'npm install'

				echo 'run npm ci'
				sh 'npm ci'

				echo 'check node version'
				sh 'node --version'
			}
		}
	}
}
