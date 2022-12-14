 pipeline {
    agent any
    parameters{
	string(USER_NAME, Anonymous, Enter your name)
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
		echo "your name is ${USER_NAME}"
            }
        }
        stage('-------------------Start test-------------------'){
            steps{
                echo "Testing the app"
		withCredentials([
		    usernamePassword(credentialsId: 'ubuntu-ansible', usernameVariable: 'USER', passwordVariable: 'PWD')
		]) {
		   echo " ${USER}, ${PWD}"
		}
            }
        }
    }
}
