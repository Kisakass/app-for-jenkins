 pipeline {
    agent any
    parameters{
	string(name:'USER_NAME', defaultValue:'Anonymous', description: 'Enter your name')
	choice(name:'FAVORITE_COLOR', choices['red', 'gree', 'yellow'], description: "Choise your favorite color"
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
		echo "your name is ${params.USER_NAME}"
		echo "your favorite color is ${params.FAVORITE_COLOR"}
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
