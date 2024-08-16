@Library('library')_

pipeline
{
    agent any
    stages
    {
        stage('ContDownload_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('ContBuild_Master')
        {
            steps
            {
                script
                {
                    cicd.buildArtifact()
                }
            }
        }
        stage('ContDeployment_Master')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.82.221","testapp")
                }
            }
            
        }
        stage('ContTesting_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("FunctionalTesting")
                    cicd.runSelenium("DeclarativePipelinewithSharedLibraries")
                }
            }
        }
        stage('ContDelivery_Master')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.85.138","prodapp")
                }
            }
        }
        
        
        
        
        
    }
}
