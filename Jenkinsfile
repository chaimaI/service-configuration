pipeline{
    agent any
    triggers{
		pollSCM('* * * * *')
	}
    stages{
        stage("Compile the source code")	{
            steps	{
            bat "./mvnw compile"
            }
        }
      
	stage("Package the application")	{
            steps	{
            bat "./mvnw clean package -DskipTests"
            }
        }
	
	stage("Deploy to the staging")	{
	    steps	{
	    bat	"mvn spring-boot:run"
	}
	}
    }
}
