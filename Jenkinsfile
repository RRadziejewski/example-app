node {
	def app
	stage('Clone repository') {
		checkout scm
	}

	stage('Build image'){
		app = docker.build('akante/example-app')
		
	
	}
	
	stage('Test') {
		app.inside {
			sh 'npm test'
		}
	
	}
	stage('Push image') {
		docker.withRegistry('https://registry.hub.docker.com','Dockerhub'){
			app.push('latest')
		}
	
	}
	

}
