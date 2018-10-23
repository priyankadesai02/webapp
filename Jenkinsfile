pipeline {
    agent any
    tools {
        maven 'MAVEN_HOME'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    stage ('Copy WAR'){
     steps{
        sh """
           ssh -tt root@18.222.7.5 sudo cp /var/lib/jenkins/workspace/WebappPipeline/target/WebApp.war /opt/Dockerstuff
           """
        }
    }
    }
}
