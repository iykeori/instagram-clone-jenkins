pipeline{
    agent any
    stages{
        stage("run frontend"){
            steps {
                echo 'executing commands...'
                sh 'sudo su'
                sh 'yum update -y && \
                    yum install -y httpd && \
                    yum search wget && \
                    yum install wget -y && \
                    yum install unzip -y'
                sh 'cd /var/www/html'
                sh 'wget https://github.com/iykeori/instagram-clone/archive/master.zip'
                sh 'unzip master.zip'
                sh 'cp -r instagram-clone/* /var/www/html/'
                sh 'rm -rf instagram-clone master.zip'
                sh 'netstat -na | grep :8080'
                sh 'netstat -na | grep :8080'
            }
        }
        stage("run backend"){
            steps {
                echo 'finished...'
            }
        }
    }
}