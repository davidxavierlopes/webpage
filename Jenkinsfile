// Powered by Infostretch 

timestamps {

node () {

	stage ('webpage - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'e28ccbea-be9f-40b5-9c88-e39385df0a4a', url: 'https://github.com/davidxavierlopes/webpage.git']]]) 
	}
	stage ('webpage - Build') {
 			// Shell build step
sh """ 
sudo docker stop web || true 
 """		// Shell build step
sh """ 
sudo docker build -t webserver /root/webpage
sudo docker run -it --rm -d -p 8081:80 --name web webserver 
 """ 
	}
}
}