node {

    stage("Git Clone"){

        git credentialsId: 'GIT_CREDENTIALS', url: 'https://github.com/Shyam-Ravindran/jenkinspipeline.git'
    }

    stage("Docker build"){
        sh 'docker version'
        sh 'docker build -t sshyam003/shyam .'
        sh 'docker image list'
        sh 'docker tag sshyam003/shyam sshyam003/shyam:latest'
    }

    withCredentials([string(credentialsId: 'e2fafbb6-1d17-4801-8301-635d885dbf0a', variable: 'PASSWORD')]) {
        sh 'docker login -u sshyam003 -p $PASSWORD'
    }

    stage("Push Image to Docker Hub"){
        sh 'docker push  sshyam003/shyam:latest'
    }

    stage("SSH Into k8s Server") {
    withCredentials([string(credentialsId: 'aa530813-a91c-4702-9b24-0bda648f0475', variable: 'SSH_PRIVATE_KEY')]) {
        ssh -i $SSH_PRIVATE_KEY ubuntu@107.21.83.221 "uname -a"
    }
    
}
}
 

