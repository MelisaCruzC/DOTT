pipeline {
	agent any
		stages {
			stage('Clon') {
				steps {
					git 'https://github.com/MelisaCruzC/DOTT.git'
				}
			}


			stage('Analysis') {
				def scannerHome = tool 'sonarqube';
				withSonarQubeEnv('sonarqube'){
					sh "${scannerHome}/bin/sonar-scanner \
					-D sonar.login=admin \
					-D sonar.password=admin \
					-D sonar.projectKey=ProjectDOTT \
					-D sonar.host.url=http://18.118.2.29:9000/"
					}
			} 

			stage('Test') {
				steps {
					sh 'echo "Step Three"'
				}
			}
			stage('Deploy') {
                                steps {
                                        sh 'echo "Prueba"'
                                }
                        }

		}
}

