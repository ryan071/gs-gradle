node{
	def myGradleContainer = docker.image('gradle:jdk11')
	myGradleContainer.pull()
	stage('prep'){
		checkout scm
	}
	
	stage(test) {
		myGradleContainer.inside("-u 0 -v ${env.HOME}/ .gradle:/home/gradle/ .gradle") {
			sh 'cd complete && ./gradlew test'
		}
	}
	
}
