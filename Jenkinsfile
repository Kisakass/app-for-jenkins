pipeline {
    agent any
    stages {
        stage ("-----------------Start building----------------"){
            when{
                expression{
                    env.BRANCH_NAME == 'master'
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
