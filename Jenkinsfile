pipeline { 
	agent any
	triggers {
		pollSCM("* * * * *")
	}
	stages {
		stage("Build"){
			steps {
				bat "docker compose build"
			} 
		} 
		stage("Test"){
			steps {
				bat "docker compose test-service"
			}
		}  
		stage("Deliver"){
			steps {
				bat "docker compose push" 
			}
		} 
	}
}