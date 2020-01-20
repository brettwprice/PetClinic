// Powered by Infostretch 

timestamps {

node () {

	stage ('PetClinic - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'bebb3e8f-5ec7-498b-b8b4-7cb8ba3ad107', url: 'https://github.com/brettwprice/PetClinic.git']]]) 
	}
	stage ('PetClinic - Build') {
 			// Maven build step
	withMaven(maven: 'Manven') { 
 			if(isUnix()) {
 				sh "mvn -f build/pom.xml package " 
			} else { 
 				bat "mvn -f build/pom.xml package " 
			} 
 		}		// Shell build step
sh """ 
mv $WORKSPACE/build/target/spring-petclinic-1.5.1.jar $WORKSPACE/build/petclinic/spring-petclinic.jar 
 """		// Shell build step
sh """ 
7za a -tzip petclinic.zip "$WORKSPACE/build/petclinic/*" 
 """ 
	}
	stage ('PetClinic Deployment Cloud Center - Build') {
 	
// Unable to convert a build step referring to "cliqr.jenkins.plugin.CliQrJenkinsClient.CliQrJenkinsClientBuilder". Please verify and convert manually if required. 
	}
}
}