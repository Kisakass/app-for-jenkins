 pipeline {
    agent any
    environment{ 
        NEW_VERSION='1.3.0'
    }    
    stages {
        stage ("-----------------Start building----------------"){
            when{
                expression{ branch "master" }
            }
            steps{
                echo "Building app version ${NEW_VERSION}"
            }
        }
        stage('-------------------Start test-------------------'){
            steps{
                echo "Testing the app"
		withCredentials([
		    usernamePassword(credentials: 'ubuntu-ansible', usernameVariable: USER, passwordVariable: PWD)
		]) {
		   sh "some script ${USER}, ${PWD}"
		}
            }
        }
    }
}
