## Sonarqube Installation Process
# 1. Install the latest Java
    $ sudo yum install java-1.8.0
# 2. Install Sonarqube
    $ cd /opt
    $ wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-7.6.zip
# Unzip the folder
    $ sudo unzip sonarqube-7.6.zip
# Ading new user and giving an admin rights
    $ useradd sonar
    $ visudo 
    Ex: (sonar   ALL=(ALL)       NOPASSWD:ALL )
#  Change the user group and file permissions
    $ chown -R sonar:sonar /opt/sonarqube-7.6
    $ chmod -R 775 /opt/sonarqube-7.6/
# Login in to Sonar user and start the sonarqube
    $ su - sonar
    $ cd /opt/sonarqube-7.6/bin/linux-x86-64
    $ ./sonar.sh start
# Enable the 9000 sg and use the sonarqube in the web
    ex: http://54.90.205.176:9000/

# To copy Existing Git repo to New Repo
    git remote add origin https://github.com/cheerlavamsi/Selenium.git
    git push -u origin master
# Another Method
    Mirroring a repository
    Open Git Bash.
    Create a bare clone of the repository.
    $ git clone --bare https://github.com/exampleuser/old-repository.git
    Mirror-push to the new repository.
    $ cd old-repository.git
    $ git push --mirror https://github.com/exampleuser/new-repository.git
    Remove the temporary local repository you created earlier.
    $ cd ..
    $ rm -rf old-repository.git




