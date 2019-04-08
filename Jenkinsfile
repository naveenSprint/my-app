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
}
