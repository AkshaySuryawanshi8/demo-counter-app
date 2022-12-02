pipeline{
    
    agent any 
    
    stages {
        
        stage('Git Checkout'){
            
            steps{
                
                script{
                    
                    git branch: 'main', url: 'https://github.com/AkshaySuryawanshi8/demo-counter-app.git'
                }
            }
        }
        stage('UNIT Testing'){
            
            steps{
                    sh 'mvn test'
            }
        }
        stage('Integration testing'){

            steps{
                sh 'mvn verify -DskipUnitTests'
            }
        }
        stage('Maven Build'){

            steps{
                sh 'mvn clean install'
            }
        }
        stage('Deploy jar file to Tomcat Server'){
            steps{
                sshagent(['Tomcat_Deploy_user']) {
                    sh 'scp -o StrictHostKeyChecking=no /app.target/Uber.jar ec2-user@52.66.88.54:/opt/digital/tomcat/webapp'
                    
}
                }
            }
        }
        
}
