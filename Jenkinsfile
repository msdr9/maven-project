pipeline{
    agent any
    tools {
        maven 'mymaven'
    }   

    stages{
            
        stage('build')
        {
            steps{
                sh 'mvn clean package'
            }
        }
    }
    
}