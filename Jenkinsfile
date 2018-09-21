node{
	stage('SCM Check Out'){
		git 'https://github.com/csaminen/app.git'
	}
	stage('Maven Packaging'){
		//Getting maven home path
		def mavenHome = tool name: 'maven3', type: 'maven'
		sh "${mavenHome}/bin/mvn package"
	}
}
