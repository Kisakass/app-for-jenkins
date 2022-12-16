pipeline{
   agent any
   environment{
	APP_VERSION='1.3.0'
   }
   stages{
      stage("Start building app") {
         steps{
            echo "Start Building app echo"
	    echo "envrionment variable ${APP_VERSION}"
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
         }
      }
   }
}
