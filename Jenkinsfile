node{
   stage('SCM Checkout'){
       git credentialsId: 'be0306bf-b315-41f2-aad8-e09600f13e51', url: 'https://github.com/iykeori/instagram-clone-jenkins.git'
   }
   
   stage('Build Docker Image'){
     sh 'docker build -t iykeori/instagram-clone .'
   }
   stage('Push Docker Image'){
     withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
        sh ('docker login -u iykeori -p ${dockerHubPwd}')
       
    }
    
    sh 'docker push iykeori/instagram-clone'
   }
  
}