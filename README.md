# Tomcat
sudo yum install java-1.8.0-openjdk

sudo yum install java-1.8.0-openjdk-devel

cd /opt

wget https://mirrors.sonic.net/apache/tomcat/tomcat-8/v8.5.59/bin/apache-tomcat-8.5.59.tar.gz

mkdir tomcat

 tar xzvf apache-tomcat-8.5.59.tar.gz -C /opt/tomcat/ --strip-components=1
 
 sudo groupadd tomcat
 
 sudo useradd -s /bin/false -g tomcat -d /opt/tomcat tomcat
 
 chmod -R 755 /opt/tomcat/

 chown -R tomca:tomcat /opt/tomcat
 
 systemctl enable tomcat
 
 systemctl daemon-reload
 
 systemctl start tomcat
 
