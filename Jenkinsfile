node {

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

    stage("SSH Into minukube server") {
        sh 'scp -i ~/home/ec2-user/rowdy.pem ./nginx ubuntu@107.21.83.221:~/'
        sh 'ssh -i ~/home/ec2-user/rowdy.pem ubuntu@107.21.83.221 "helm install myfirstnginxchart nginx"'
    }
}
 

