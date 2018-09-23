node{
	stage('SCM Check Out'){
		git 'https://github.com/csaminen/app.git'
	}
	stage('Maven Packaging'){
		//Getting maven home path
		def mavenHome = tool name: 'maven-3.5.4', type: 'maven'
		sh "${mavenHome}/bin/mvn package"
	}
	
	stage('Deploy to Tomcat'){

		sshagent(['EC2-Slave']){
			sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@18.212.207.99:/opt/apache-tomcat-8.5.34/webapps'
		}

	}
	stage('Email Notification'){
		mail bcc: '', body: 'Deployed Successfully', cc: '', from: '', replyTo: '', subject: 'Deployed Successfully', to: 'chinnarsamineni@gmail.com'

	}

	
	
	
	//stage('Installing Docker'){
		//pwd()
		//sh aws pwd
		//sh 'sudo su'
		//sh 'yum update -y'
		//sh 'yum install docker -y'
		//sh 'service docker start'
		//For adding the ec2-user to the docker group so we can execute Docker commands without using sudo.
		//sh 'sudo usermod -a -G docker ec2-user'
	//}
}
