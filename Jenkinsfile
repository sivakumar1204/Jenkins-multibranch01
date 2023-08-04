pipeline {
    agent any

    stages {
        stage('Continuous Download_loans') 
		{
            steps 
			{
                script 
				{
                    // Define the URL of the Git repository you want to clone
                    def gitRepoUrl = 'https://github.com/sunildevops77/maven.git'
                    
                    // Clone the repository into a workspace directory
                    git branch: 'master', url: gitRepoUrl
                }
            }
        }
        stage('Continuous Build_loans') 
		{
            steps 
			{
                script 
				{                    
                    sh 'mvn clean package' // Specify your Maven goals here
                    
				}
            }
        }
	stage('Continuous Deployment') 
		{
			steps 
			{
                sshagent(['ubuntu-tomcat-server-2']) 
				{
					sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.16.74:/home/ubuntu/apache-tomcat-8.5.91/webapps/QAENV.war'
				}
            }
        }
	stage('Continuous Test_loans') 
		{
            steps 
			{
                script 
				{                    
                    sh 'echo "Tesing Passed!"'
                    
				}
            }
        }
	}
}
