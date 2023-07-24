1. Create sonar user to manage the SonarQube server
#As a good security practice, SonarQuber Server is not advised to run sonar service as a root user, 
# create a new user called sonar and grant sudo access to manage sonar services as follows

sudo useradd sonar
# Grand sudo access to sonar user
sudo echo "sonar ALL=(ALL) NOPASSWD:ALL" | sudo tee /etc/sudoers.d/sonar
# set hostname for the sonarqube server
sudo hostnamectl set-hostname sonar 
sudo su - sonar
1b. Assign password to sonar user
sudo passwd sonar
2. Enable PasswordAuthentication in the server
sudo sed -i "/^[^#]*PasswordAuthentication[[:space:]]no/c\PasswordAuthentication yes" /etc/ssh/sshd_config
sudo service sshd restart
## Sonarqube Installation Process
# 1. Install the latest Java, wget, git & unzip
 $ cd /opt
 sudo yum -y install unzip wget git
    $ sudo yum install java-1.8.0
# 2. Install Sonarqube
   $ wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-7.6.zip
# Unzip the folder
    $ sudo unzip sonarqube-7.6.zip
    sudo rm -rf sonarqube-7.6.zip
sudo mv sonarqube-7.6 sonarqube

#  Change the user group and file permissions
    $ chown -R sonar:sonar /opt/sonarqube-7.6
    $ chmod -R 775 /opt/sonarqube-7.6/
    
**6. start sonarQube server**
sh /opt/sonarqube/bin/linux-x86-64/sonar.sh start 
sh /opt/sonarqube/bin/linux-x86-64/sonar.sh status
7. Ensure that SonarQube is running and Access sonarQube on the browser
sonarqube default port is = 9000
get the sonarqube public ip address
publicIP:9000

    $ cd ..
    $ rm -rf old-repository.git




