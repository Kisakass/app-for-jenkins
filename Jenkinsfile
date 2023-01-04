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
					usernamePassword(credentialsid: "github-ssh-key", UsernameVariable: USER, passwordVariable: PWD) {
						echo "credentials is: $USER and pwd is $PWD"
					}
				])
			}
		}
	}
}
