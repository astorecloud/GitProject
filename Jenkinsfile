pipeline 
{
    agent any

    stages 
    {
        stage ('Stop Container') 
        {
            steps 
            {
               script{
                    sh 'docker stop imagetest'
                }
            }
        }
    }    
        stage('Remove Container') 
        {
            steps 
            {
                script {
                    sh 'docker rm imagetest'
                }
            }
        }
         stage('Remove Container Image') 
        {
            steps 
            {
                script {
                    sh 'docker rmi imagetest '
                }
            }
        }
        stage('Build docker image') 
        {
            steps 
            {
                script{
                    sh 'docker build -t imagetest .'
                }
            }
        }
        stage('Build docker Container') 
        {
            steps 
            {
                script{
                    sh 'docker run -d --name testcontainer -p 8181:80 imagetest '
                }
            }
        }
    
    post 
    {   
        always
        {
            emailext body: 'Summary', subject: 'Pipeline status', to: 'ahsan@gmail.com'
        }

    }
}
