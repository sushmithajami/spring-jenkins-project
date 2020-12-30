pipeline {
    agent { label "Windows_10" }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
		stage('Application_Build_Batch') {
            steps {
                bat '''mvn clean package -DskipTests
                echo %BUILD_URL%'''
            }
        }
        stage('Application_Build_Unit_test') {
            steps {
                bat 'mvn -Dfilename=testng-unit.xml test'
            }
        }
    }
}