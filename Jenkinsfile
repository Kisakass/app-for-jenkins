pipeline {
    agent any
    stages {
        stage ("-----------------Start building----------------"){
            when{
                expression{
                    BRANCH_NAME == 'main'
                }
            }
            steps{
                echo "Building the app"
            }
        }
        stage('-------------------Start test-------------------'){
            steps{
                echo "Testing the app"
            }
        }
    }
}
