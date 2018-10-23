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
        stage ('Run Ansible playbook'){
	    steps{
		sh """
			ssh -tt root@18.222.7.5 sudo ansible-playbook /opt/AnsibleControl/DockerPlaybook.yml
                """
	    }
       }
}
