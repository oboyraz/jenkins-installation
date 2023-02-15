# Part 1 - Installing Jenkins Server on Amazon Linux 2 with yum Repo
- Update the installed packages and package cache on your instance.
````
   sudo yum update -y
````
- Install Java 11 openjdk Java Development Kit.
````
sudo amazon-linux-extras install java-openjdk11 -y
````bash
- Check the java version.
````bash
java -version
````
- Add Jenkins repo to the yum repository.
````bash
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat/jenkins.repo
````
- Import a key file from Jenkins-CI to enable installation from the package.
````bash
sudo rpm --import https://pkg.jenkins.io/redhat/jenkins.io.key
````
- Enable the EPEL repository for Amazon EC2 instance.
````bash
sudo amazon-linux-extras install epel
````
- Install Jenkins.
````bash
sudo yum install jenkins -y
````
- Start Jenkins service.
````bash
sudo systemctl start jenkins
````
- Enable Jenkins service so that Jenkins service can restart automatically after reboots.
````bash
sudo systemctl enable jenkins
````
- Check if the Jenkins service is up and running.
````bash
sudo systemctl status jenkins
````
- Get the initial administrative password.
````bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
````
- Open your browser, get your ec2 instance Public IPv4 DNS and paste it at address bar with 8080. "http://[ec2-public-dns-name]:8080"
- Enter the temporary password to unlock the Jenkins.
- Install suggested plugins.
- Create first admin user (call-jenkins:Call-jenkins1234).
- Check the URL, then save and finish the installation.
