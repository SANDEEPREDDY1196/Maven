@Library('mylibrary')_

pipeline
{
    agent any
    stages
    {
        stage('Cont Download_Master')
        {
            steps
            {
                script
                {
                    cicd.GitDownload("Maven")
                }
            }
        }
        
        stage('Cont Build_Master')
        {
            steps
            {
                script
                {
                    cicd.BuildArtifact()
                }
            }
        }
        
        stage('Cont Deploy_Master')
        {
            steps
            {
                script
                {
                    cicd.DeployQAServer("SharedLibraryWithDeclarativePipeline","172.31.6.23", "QATest")
                }
            }
        }
        
        stage('Cont Testing_Master')
        {
            steps
            {
                script
                {
                    cicd.GitDownload("FunctionalTesting")
                    cicd.RunSelinium("SharedLibraryWithDeclarativePipeline")
                }
            }
        }
        
        stage('Cont Delivery_Master')
        {
            steps
            {
                script
                {
                    cicd.DeliveryonProd("SharedLibraryWithDeclarativePipeline","172.31.15.141", "ProdTest")
                }
            }
        }
    }
}
