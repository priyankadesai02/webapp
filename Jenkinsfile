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
           scp -pr /var/lib/jenkins/workspace/WebappPipeline/target/WebApp.war root@18.222.7.5:/opt/Dockerstuff
           """
        }
    }
    }
}
