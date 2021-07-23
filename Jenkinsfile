node {

        stage('SCM') {
                git credentialsId: '4e523118-02bb-453d-9877-045d3a449410', url: 'https://github.com/MelisaCruzC/DOTT.git'
        }

	stage ('Compile'){
		def mvnHome = tool name: 'MavenSQ', type: 'maven'
		sh "mvn -f cidr_convert_api/java/cidr-api/pom.xml clean install"
	}

        stage('Analysis') {
                def mvnHome = tool name: 'MavenSQ', type: 'maven'
                withSonarQubeEnv('sonarqube'){
                        sh "${mvnHome}/bin/mvn sonar:sonar \
                        -D sonar.login=admin \
                        -D sonar.password=admin \
			-Dsonar.login=e83ec5f9b38e527376ccc2485f508cf42d59439e \
			-D sonar.verbose=true \
                        -D sonar.projectKey=ProjectDOTT \
                        -D sonar.host.url=http:/http://3.136.233.246:9000/"
                }
        } 

	stage('Test') {
		sh 'echo "Step Three"'
	}

	stage('Deploy') {
		sh 'echo "Prueba"'
	}

}


