pipeline { 
	agent {
        label 'unix-agent'
    }
	triggers {
		pollSCM("* * * * *")
	}
	stages {
		stage("Build"){
			steps {
				sh "docker compose build"
			} 
		} 
		stage("Test"){
			steps {
				sh "docker compose test-service"
			}
		}  
		stage("Deliver"){
			steps {
				sh "docker compose push" 
			}
		} 
	}
}