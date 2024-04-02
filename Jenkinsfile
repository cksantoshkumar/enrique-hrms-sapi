pipeline{  
agent any 
stages{ 
stage('BuildApplication') { 
steps { 
bat 'mvn clean install' 
} 
} 
stage('DeployCloudHubs') { 
environment { 
ANYPOINT_CREDENTIALS = credentials(' anypointplatformcredentials ') 
} 
steps { 
echo 'Deploying mule project due to the latest code commit…' 
echo 'Deploying to the configured environment….' 
bat 'mvn clean deploy -DmuleDeploy  
-Dusername=${ANYPOINT_CREDENTIALS_USR} -
Dpassword=${ANYPOINT_CREDENTIALS_PSW} 
-DworkerType=Micro -Dworkers=1' 
}  
} 
} 
}
