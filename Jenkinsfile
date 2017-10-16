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
                                publishHTML (target: [
                  			reportDir: 'build/reports/jacoco/test/html',
                  			reportFiles: 'index.html',
                  			reportName: "JaCoCo Report"
				])
             			sh "./gradlew jacocoTestCoverageVerification"
       	 		}
		}
	   }

          
          stage("Static code analysis") {
      	       steps {
			ws ('/var/jenkins/') {        
				sh "./gradlew checkstyleMain"
        			publishHTML (target: [
               				reportDir: 'build/reports/checkstyle/',
               				reportFiles: 'main.html',
               				reportName: "Checkstyle Report" ])
      			}
    		}	
  
	  }
            
   }
}
