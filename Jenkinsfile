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
					def list = sh returnStdout: true, script: "ls"
					def choice_params = []
					list.split("\n").each { str ->
						println str.trim()
						choice_params.add(str.trim())
					}
					
					def input_data = input id: '123213213', message: 'dafd', parameters: [
							booleanParam(defaultValue: false, description: '1234', name: 'ert'),
							booleanParam(defaultValue: true, description: '2345', name: 'edc'),
							new ChoiceParameterDefinition("choice_1", choice_params, "Example")
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
