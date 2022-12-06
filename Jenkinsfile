node{
	def myGradleContainer = docker.image('gradle:jdk11')
	myGradleContainer.pull()
	stage('prep'){
		checkout scm
	}
	
	stage(test) {
		myGradleContainer.inside("-v /var/jenkins_home/workspace/ .gradle:/home/gradle/ .gradle") {
			sh 'cd complete && gradle test'
		}
	}
	
}
