# Tomcat installation on REDHAT
1. Install the Open JDK

sudo yum install java-1.8.0-openjdk

sudo yum install java-1.8.0-openjdk-devel

2. Download the tomcat and create the tomcat directory  on /opt
   cd /opt

   wget https://mirrors.sonic.net/apache/tomcat/tomcat-8/v8.5.59/bin/apache-tomcat-8.5.59.tar.gz

mkdir tomcat

3. Untar it on /opt/tomcat

    tar xzvf apache-tomcat-8.5.59.tar.gz -C /opt/tomcat/ --strip-components=1
 
 4. Create the tomcat group
 
    sudo groupadd tomcat
 
 5. Next, create a new tomcat user. We’ll make this user a member of the tomcat group, with a home directory of /opt/tomcat (where we will install Tomcat), and with a shell of /bin/false (so nobody can log into the accounnt)
 
   sudo useradd -s /bin/false -g tomcat -d /opt/tomcat tomcat
 
 6. Access to the install directory
 
     chmod -R 755 /opt/tomcat/
 
 7.Change  owner and group  ownership of install directory to tomcat

    chown -R tomcat:tomcat /opt/tomcat
 
 8. Copy the tomcat.service( available in the same repo) to the /etc/systemd/system
 
 9. Enable the tomcat service
 
    systemctl enable tomcat
 
 10. Reload the daemon
 
     systemctl daemon-reload
 
 11. Start the tomcat service
 
    systemctl start tomcat
 
