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
        stage('Deploy') 
        {
            steps 
            {
                echo 'Deploy App'
            }
        }
    }
    post 
    {   
        always
        {
            emailext body: 'Summary', subject: 'Pipeline status', to: 'astorecloud@gmail.com'
        }

    }
}
