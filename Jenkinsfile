pipeline{
   agent none
        stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('SONAR_HOME') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
	}	
}
