@Library('library')_

pipeline
{
    agent any
    stages
    {
        stage('ContDownload_Loans')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('ContBuild_Loans')
        {
            steps
            {
                script
                {
                    cicd.buildArtifact()
                }
            }
        }
        
    }
}
