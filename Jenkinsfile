node{
    def mvnHome = tool name: 'Maven 3.5', type: 'maven'
    def mvn = "${mvnHome}/bin/mvn"
    stage('Git Checkout'){
	   git branch: 'master', 
	       credentialsId: 'github', 
		   url: 'https://github.com/naveenSprint/my-app'
	}
	
	stage('Build'){
	   sh "${mvn} clean package"   
	}
	stage('deploy-to-dev'){
	  sshagent(['tomcat-dev']) {
		sh 'scp -o StrictHostKeyChecking=no target/*.war naveen@192.168.56.101:/opt/apache-tomcat-9.0.0.M10/webapps/'
	}
}
}
