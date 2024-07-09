pipeline{
    agent any
    parameters {
        string defaultValue: 'Maddineni', name: 'LASTNAME'
    }
    environment{
        NAME = "Dharma"
    }
    
    tools {
        maven 'mymaven'
    }   
    
    stages{
            
        stage('build')
        {
            steps{
                sh 'mvn clean package'
                echo "hello $NAME ${params.LASTNAME}"
            }
        
            post{
                success{
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
    
}