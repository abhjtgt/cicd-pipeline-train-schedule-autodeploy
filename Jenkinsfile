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
                sh 'echo "./gradlew build --no-daemon"'
            }
        }
	}
}
