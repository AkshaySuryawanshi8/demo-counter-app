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
        
}
}
