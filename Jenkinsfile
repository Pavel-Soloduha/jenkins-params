library 'lib'

pipeline {

	agent {
		docker {
			image "alpine"
			args "-u root"
		}
	}

	stages {

		stage("Input params") {
			steps {
				script {
					CustomInput.addInput()
				}
			}
		}
	}
}
