pipeline{
    agent any
    environment{
        NEW_VERSION= '1.3.0'
        SERVER_CREDENTIALS= credentials('SERVER_CREDENTIALS_user')
    }
    parameters{
        string(name : "VERSION1", defaultValue: "1.0.0", description : "This is used to mention the version details")
        choice(name : 'VERSION', choices: ['1.0.2', '1.4.3','2.4.6'], description:'')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
        
    }
    stages{
        stage('build'){
            steps{
                echo "This is a sample building block"
                echo "Building version is ${NEW_VERSION}"
                echo "The AWS key is ${SERVER_CREDENTIALS}"
            }
            
        }
        stage('test'){
            when{
                expression{
                   params.excuteTests == true
                }
            }
            steps{
                echo "This is testing the application"
                echo "Deploying version ${VERSION}"
                echo "Deploying version ${VERSION1}"
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
