
node{
	stage('SCM Check Out'){
		git clone 'https://github.com/csaminen/app.git'
	}
	stage('Maven Packaging'){
		mvn clean package
	}

}
