pipeline 
{
    agent any 
    stages
    {
        stage('ContinuousDownload')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/Maven.git'
            }
        }
        stage('ContinuousBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContinuousDeploy')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/DeclarativePipeline1/webapp/target/webapp.war ubuntu@172.31.6.23:/var/lib/tomcat10/webapps/mytestapp.war'
                
            }
        }
        stage('ContinuousTesting')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/DeclarativePipeline1/testing.jar'
            }
        }
        stage('ContinuousDelivery')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/DeclarativePipeline1/webapp/target/webapp.war ubuntu@172.31.15.141:/var/lib/tomcat10/webapps/myprodapp.war'
            }
        }
        
    }
}
