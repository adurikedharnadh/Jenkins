pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                echo "This is a sample building block"
            }
            
        }
        stage('test'){
            when{
                expression{
                    env.BRANCH_NAME == "dev" || BRANCH_NAME == "Feature"
                }
            }
            steps{
                echo "This is testing the application"
            }
            
        }
        stage('deploy'){
            when{
                expression{
                    BRANCH_NAME == "main"
                }
            }
            steps{
                echo "Here we are deploying the application "
            }
            
        }
    }
    
    
}
