pipeline{
	agent any
	environment {
		MY_NAME= 'sasha'
	}
	stages{
		stage("build") {
			steps {
				echo "----------------------start building-----------------------"
				echo "Your name is $MY_NAME"
			}
		}
		stage("test") {
			steps{
				withCredentials([
					usernamePassword(credentialsId: 'github-ssh-key', usernameVariable: 'USER', passwordVariable: 'PWD') ]) {
						echo "some code $USER and $PWD"
					}
			}
		}
	}
}
