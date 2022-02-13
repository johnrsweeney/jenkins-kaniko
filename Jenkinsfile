pipeline {
	agent {
		docker { image 'gcr.io/kaniko-project/executor:debug' }
		args '--entrypoint ""'
	}
	environment {
		CI_REGISTRY='https://index.docker.io/v1/'
		CI_REGISTRY_USER=johnswe
	}
	stages {
		stage('Build & Push Image') {
			steps {
				sh 'echo testing...'
			}
		}
	}
}
