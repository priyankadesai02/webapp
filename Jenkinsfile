pipeline {
    agent any
    tools {
        maven 'MAVEN_HOME'
    }
	stages {
	stage("build & SonarQube analysis") {
          node {
              withSonarQubeEnv('My SonarQube Server') {
                 sh 'mvn clean package sonar:sonar'
              }
          }
}
}
}
