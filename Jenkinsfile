node{
	stage('SCM Check Out'){
		git 'https://github.com/csaminen/app.git'
	}
	stage('Maven Packaging'){
		//Getting maven home path
		def mavenHome = tool name: 'maven3', type: 'maven'
		sh "${mavenHome}/bin/mvn package"
	}
	stage('Installing Docker'){
		sh pwd
		//sh 'sudo su'
		//sh 'yum update -y'
		//sh 'yum install docker -y'
		//sh 'service docker start'
		//For adding the ec2-user to the docker group so we can execute Docker commands without using sudo.
		//sh 'sudo usermod -a -G docker ec2-user'
	}
}
