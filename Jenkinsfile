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
					usernamePassword(credentials: "github-ssh-key", usernameVariable: USER, passwordVariable: PWD) ]) {
						sh "some code $USER and $PWD"
					}
			}
		}
	}
}
