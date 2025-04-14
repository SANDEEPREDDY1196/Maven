@Library('mylibrary')_

pipeline
{
    agent any
    stages
    {
        stage('Cont Download_Loan')
        {
            steps
            {
                script
                {
                    cicd.GitDownload("Maven")
                }
            }
        }
        
        stage('Cont Build_Loan')
        {
            steps
            {
                script
                {
                    cicd.BuildArtifact()
                }
            }
        }
        
        
    }
}
