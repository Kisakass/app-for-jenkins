nano pipeline{
	agent any
	environment {
		MY_NAME= 'sasha'
	}
	parameters{
		string(name:'NAME', defaultValue: 'Anonymous', description: 'Enter your name')	
		choice(name: 'CHOICES', choices: ['red', 'green'], description: 'Choose')
		boolen(name: 'Are you gay?', defaultValue: 'yes', description: 'say yes')
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
					usernamePassword(credentialsId: 'ubuntu-ansible', usernameVariable: 'USER', passwordVariable: 'PWD') ]) {
						echo "some code $USER and $PWD"
					}
			}
		}
		stage("stage-3") {
			steps {
				echo "Your name is $NAME"
				echo "ck $CHOICES"
			}
		}
	}
}
