pipeline{  
agent any 
stages{ 
stage('Build Application') { 
steps { 
bat 'mvn -U clean install' 
} 
} 
stage('Deploy CloudHubs') { 
environment { 
ANYPOINT_CREDENTIALS = credentials(' anypoint.creds ') 
} 
steps { 
echo 'Deploying mule project due to the latest code commit…' 
echo 'Deploying to the configured environment….' 
bat 'mvn clean deploy -DmuleDeploy -Dusername=cksantoshkumar123 -Dpassword=Santoshck@50 -DworkerType=Micro -Dworkers=1' 
}  
} 
} 
}
