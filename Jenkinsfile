node {

	stage('SCM') {
		git credentialsId: '4e523118-02bb-453d-9877-045d3a449410', url: 'https://github.com/MelisaCruzC/DOTT.git'
	}

	stage('Analysis') {
		def scannerHome = tool 'ScannerSQ';
		withSonarQubeEnv('ServerSQ'){
			sh "${scannerHome}/bin/sonar-scanner \
			-D sonar.login=admin \
			-D sonar.password=admin \
			-D sonar.verbose=true \
			-D sonar.projectKey=ProjectDOTT \
			-D sonar.host.url=http://3.136.233.246:9000/"
		}
	} 

	stage('Test') {
		sh 'echo "Step Three"'
	}

	stage('Deploy') {
		sh 'echo "Prueba"'
	}

}


