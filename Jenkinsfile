 pipeline {
    agent any
    parameters{
	string(name:'USER_NAME', defaultValue:'Anonymous', description: 'Enter your name')
    }
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
		   echo " ${params.USER}, ${params.PWD}"
		}
            }
        }
    }
}
