node{
	def myGradleContainer = docker.image('gradle:jdk11')
	myGradleContainer.pull()
	stage('prep'){
		checkout scm
	}
	
	stage('test'){
		myGradleContainer.inside("-v ./var/jenkins_home/jenkins/workspace .gradle:/home/gradle"){
			echo "test passed"
		}
	}
	
	
}
