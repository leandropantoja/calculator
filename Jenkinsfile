pipeline {
    agent any
    stages {

            stage("Compile") {
                steps {
	                ws ('/var/jenkins/') {
                        		      sh "./gradlew compileJava"
	                }
                }
            }
            
            
            stage("Unit test") {
                steps {
                        ws ('/var/jenkins/') {
                           		      sh "./gradlew test"
               		 }
                }
           }
            
   }
}
