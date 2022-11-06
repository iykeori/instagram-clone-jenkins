pipeline{
    agent any
    stages{
        stage("run frontend"){
            steps {
                echo 'executing commands...'
                sh 'set -eu'
                sh 'docker build  -f $IMAGE_TAG/Dockerfile -t $IMAGE_TAG .'
                sh 'docker login --username $DOCKER_HUB_USERNAME --password $DOCKER_HUB_PASSWORD'
                sh 'docker tag $IMAGE_TAG $DOCKER_HUB_USERNAME/$DOCKER_HUB_REPO_NAME'
                sh 'docker push $DOCKER_HUB_USERNAME/$DOCKER_HUB_REPO_NAME'
            }
        }
        stage("run backend"){
            steps {
                echo 'finished...'
            }
        }
    }
}




