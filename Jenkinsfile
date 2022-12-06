node{
	def myGradleContainer = docker.image('gradle:Java SE Development kit 8u221')
	myGradleContainer.pull()
	stage('prep'){
		checkout scm
	}
	
	stage('test'){
		myGradleContainer.inside("-v ${env.HOME}/ .gradle:/home/gradle"){
			sh 'cd complete && ./gradlew test'
		}
	}
	
	
}
