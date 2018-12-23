pipeline {
	agent any
	tools {
        maven 'maven-plugin'
    }
	stages {
		stage('clone repo and clean it'){
			steps {
			    sh "rm -rf my-app"
				sh "git clone https://github.com/nnelson16/my-app.git"
				sh "mvn clean -f my-app"
			}
		}
		stage('Test'){
			steps {
				sh "mvn test -f my-app"
			}
		}
		stage('Deploy'){
			steps {
				sh "mvn package -f my-app"
			}
		}
	}
}