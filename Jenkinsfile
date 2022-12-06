node{
	def myGradleContainer = docker.image('gradle:jdk8')
	myGradleContainer.pull()
	stage('prep'){
		checkout scm
	}
	
	stage('test'){
		myGradleContainer.inside("-v ${env.HOME}/ .gradle:/home/gradle"){
			echo "test passed"
		}
	}
	
	stage('run'){
		myGradleContainer.inside("-v ${env.HOME}/ .gradle:/home/gradle"){
			sh 'cd complete && ./gradlew run'
		}
	}
}
