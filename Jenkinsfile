pipeline {
	agent {
		docker {
			image 'gcr.io/kaniko-project/executor:debug'
			args '--entrypoint ""'
		}
	}
	environment {
		CI_REGISTRY='https://index.docker.io/v1/'
		CI_REGISTRY_USER='johnswe'
	}
	stages {
		stage('Build & Push Image') {
			steps {
				sh '''
					pwd
					ls -l
					ls -l /workspace/
					echo "{\"auths\":{\"${CI_REGISTRY}\":{\"auth\":\"$(printf "%s:%s" "${CI_REGISTRY_USER}" "${CI_REGISTRY_PASSWORD}" | base64 | tr -d '\n')\"}}}" > sudo /kaniko/.docker/config.json
					executor --context ./ --destination johnswe/alpine:new --force
				'''
			}
		}
	}
}
