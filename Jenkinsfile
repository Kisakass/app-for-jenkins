pipeline{
   agent any
   environment{
	APP_VERSION='1.3.0'
   }
   stages{
      stage("Start building app") {
         steps{
            echo "Start Building app echo"
	    echo "Print envrionment variable"
         }
      }
      stage("Start testing app") {
	 when{
	    expression{
		env.BRANCH_NAME=='dev'
	    }
         }
         steps{
            echo "Start testing app"
         }
      }
   }
}
