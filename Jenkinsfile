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
					def list = sh returnStdout: true, script: "ls -l"
					list.split("\n").forEach { str ->
						println str
					}
					def input_data = input id: '123213213', message: 'dafd', parameters: [
							booleanParam(defaultValue: false, description: '1234', name: 'ert'),
							booleanParam(defaultValue: true, description: '2345', name: 'edc')
						]

					println input_data
					println input_data["ert"]
					println input_data.ert
					println input_data["edc"]
					println input_data.edc
				}
			}
		}
	}
}
