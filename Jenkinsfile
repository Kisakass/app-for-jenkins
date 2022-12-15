pipeline{
    agent any
    environment{
	NEW_VERSION='1.3.0'
	STAGE_CREDENTIALS=credentials("ubuntu-ansible")
    }
    stages{
	stage("Preparing app"){
	     steps{
		echo "Preparing app"
             }
	}
        stage("Buiulding app"){
	    when {
                 expression {
		     env.BRANCH_NAME=='main'
		 }
	    }
            steps{
                echo "Building the app"
            }
        }
        stage("Testing app") {
            steps{
                echo "Testing app version ${NEW_VERSION}"
		echo "Testing for ${STAGE_CREDENTIALS}"
            }
        }
    }
}
