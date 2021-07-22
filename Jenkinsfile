pipeline {
	agent any
		tools{
		maven "Maven"
		}
		stages {
			stage('Build') {
				steps {
					git 'https://github.com/MelisaCruzC/DOTT.git'
					sh "mvn -Dmaven.test.failure.ignore=true clean package"
					sh 'echo "Building App"'
				}
			}


			stage('Analysis') {
				steps {
					sh 'echo "Step Two"'
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

