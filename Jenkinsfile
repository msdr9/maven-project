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
                echo "Hello $NAME ${params.LASTNAME}"
            }
        }

        stage('test')
        {
            parallel{
                stage('TestA'){
                    steps{
                        echo "This is Test A"
                    }
                }

                stage('TestB'){
                    steps{
                        echo "This is Test B"
                    }
                }
                stage('TestC'){
                    steps{
                        echo "This is Test C"
                    }
                }
            }
            post{
                success{
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

    }
    
}