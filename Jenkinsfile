pipeline{
    agent any
    environment{
        NEW_ VERSION= '1.3.0'
        SERVER_CREDENTIALS= credentials('SERVER_CREDENTIALS_user')
    }
    stages{
        stage('build'){
            steps{
                echo "This is a sample building block"
                echo "Building version is ${NEW_VERSION}"
                echo "The AWS key is ${SERVER_CREDENTIALS_user}"
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
