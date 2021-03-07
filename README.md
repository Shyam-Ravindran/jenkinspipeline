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

# now add docker build and publish plugins
manage jenkins-> manage plugins -> cloudbees docker build and publish plugins
create a job -> add build steps-> docker build and publish -> docker repo 
scm-> select your scm (git) -> give github repo 



