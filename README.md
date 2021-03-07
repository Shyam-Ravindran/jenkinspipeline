# aws-jenkins-minikube
Repo for Jenkins CICD using Helm and minikube
sudo amazon-linux-extras install -y docker
sudo gpasswd -a ec2-user docker
sudo systemctl enable --now docker
sudo yum install git -y

# sudo cat /var/lib/jenkins/secrets/initialAdminPassword
enter that password to the jenkins browser.
note the jenkins url (not mandatory)

# now lets create the artifact as dockerfile and push it public docker repo.
go to manage jenkins-> manage plugins-> search for docker pipelines in available and install without restart.
after docker pipelines plugins are successfully added.

# On jenkins you need to create a new credentials with docker hub account details.
manage jenkins -> manage credentials-> global-> Add credentials -> add docker hub username and password -> ok
after adding your docker hub credentials.

# add ssh pipleines plugins from jenkins
Manage Jenkins -> Manage Plugin -> Available

# now add create the piple job on jenkins and add thes scm repo and jenkins file for creating the pipeline.\
1) It will get your source code from the git and do a git clone.
2) Build the docker image
3) push the docker image to docker hub.
4) pull the image from the docker
5) deploy the application using helm chart. (ssh into minikube node and deploy the application.)






