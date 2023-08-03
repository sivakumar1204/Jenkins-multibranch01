pipeline {
    agent any

    stages {
        stage('Continuous Download')
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
        stage('Continuous Build')
		{
            steps
			{
                script
				{
                    sh 'mvn clean package' // Specify your Maven goals here

				}
            }
        }
    }
}
