pipeline{
   agent any
   parameters{
       string(name:"USERNAME", defaultValue:"Anonymous", description: "Enter your username")
       choice(name:"FAVORITE_COLOR", choices:['red', 'yellow', 'green'], description: 'choose your favorite color')
   }
   environment{
	APP_VERSION='1.3.0'
   }
   stages{
      stage("Start building app") {
         steps{
            echo "Start Building app echo"
	    echo "envrionment variable ${APP_VERSION}"
	    echo "your favorite color is ${params.FAVORITE_COLOR}"
	    echo "Hi"
         }
      }
      stage("Start testing app") {
         steps{
	    withCredentials([
		usernamePassword(credentialsId:'ubuntu-ansible', usernameVariable:'USER',passwordVariable:'passWD')
            ]) {
		   echo "user: ${USER}, password: ${passWD}"
               }
            echo "Start testing app"
	    echo "Your username is ${params.USERNAME}"
         }
      }
   }
}
