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
				echo "---------------------start testing-------------------------"
			}
		}
	}
}
