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
          
           stage("Code coverage") {
        	steps {
			ws ('/var/jenkins/') {
             			sh "./gradlew jacocoTestReport"
             			sh "./gradlew jacocoTestCoverageVerification"
       	 		}
		}
	   }

            
   }
}
