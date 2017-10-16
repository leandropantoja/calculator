pipeline {
    agent any
    stages {


           stage("Checkout") {
                steps {
                    ws ('/var/jenkins/') {
                        git url: 'https://github.com/leandropantoja/calculator.git'
                    }
                }
            }


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
