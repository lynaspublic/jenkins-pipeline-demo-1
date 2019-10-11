pipeline 
{
    agent any
    
    stages 
    {
        stage('Checkout') 
        {
            steps 
            { //Checking out the repo
                git branch: 'master', url: 'https://github.com/lynaspublic/spring-demo.git'
                sh "ls -lat"
            }
        }
    

        stage('Unit & Integration Tests') 
        {
            steps 
            {
                script 
                {
                    sh './gradlew clean test --no-daemon' //run a gradle task
                }
            }
        }

        stage('RUN BUILD') 
        {
            steps 
            {
                script 
                {
                    sh './gradlew build --no-daemon' //run a gradle task
                }
            }
        }
    }
}
