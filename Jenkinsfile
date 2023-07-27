pipeline 
{
    agent any

    stages 
    {
        stage ('Build') 
        {
            steps 
            {
                echo 'Build'
            }
        }
        stage('Test') 
        {
            steps 
            {
                echo 'Test App'
            }
        }
        stage('Build docker image') 
        {
            steps 
            {
                script{
                    sh 'docker buil -t imagetest .'
                }
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
