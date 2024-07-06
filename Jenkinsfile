pipeline {
    agent any

    stages {
        stage('Clone-Repo') {
	    	steps {
	        	https://github.com/Devi-12345/gamutkart.git
	    	}
        }
	stage('Build') {
		steps {
			sh 'mvn install'
		}
	}	
 
	stage ('Compile'){
	        steps {
			sh 'mvn clean compile'
                }
	}

	stage('Run Tests') {
	    steps {
	       sh 'mvn test'
	    }
	}

        stage('Package as WAR') {
            steps {
                sh 'mvn package'
            }
        }
	stage('Deployment') {
	   steps {
		sh 'scp target/gamutkart.war root@172.31.53.175:/root/apache-tomcat-9.0.90/webapps'
	}
    }
}
}
