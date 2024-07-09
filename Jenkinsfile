pipeline{
    agent any
   /*  agent {
        docker { 
            image 'maven:3.9.2-ibmjava' 
            args '-v /devops/scm/mvn-projects/.m2:/devops/scm/mvn-projects/.m2'
            }
        
        //docker { image 'node:16-alpine' } 
    }*/
    stages{
        stage('build')
        {
            steps{
                sh 'mvn clean package'
                //sh 'mvn -Dmaven.repo.local=/devops/scm/mvn-projects/.m2/repository clean install'
            }
            post{
                success{
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        
    }
    
}