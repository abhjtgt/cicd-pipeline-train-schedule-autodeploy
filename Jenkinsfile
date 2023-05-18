pipeline {
    agent {
        label 'jenslave'
    }    
	environment {
        //be sure to replace "bhavukm" with your own Docker Hub username
        DOCKER_IMAGE_NAME = "bhavukm/train-schedule"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
				sh '''
					java -version
					export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
					export PATH=$JAVA_HOME/bin:$PATH
					java -version
				'''
               
            }
        }
		stage('Build Docker Image') {
            when {
                branch 'master'
            }
            steps {
				sh "java -version"
                }
        }
        
		stage('Build Docker Image2') {
            when {
                branch 'try1'
            }
            steps {
				sh "java -version"
                }
        }
		
	}
}
