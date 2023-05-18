pipeline {
    agent {
        label 'jenslave'
    }    
	environment {
        //be sure to replace "bhavukm" with your own Docker Hub username
        DOCKER_IMAGE_NAME = "abhjtdk/train-schedule"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
				sh '''
				    java -version
					export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java
					export PATH=$JAVA_HOME/bin:$PATH
					java -version
				    ./gradlew build --no-daemon
					java -version
				   '''
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    app = docker.build(DOCKER_IMAGE_NAME)
                    app.inside {
                        sh 'echo Hello, World!'
                    }
                }
            }
        }
	}
}
