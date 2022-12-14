pipeline {
    agent any
    stages {
        stage ("-----------------Start building----------------"){
            when{
                expression{
                    branch "main"
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
