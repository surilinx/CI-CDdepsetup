# CI-CDdepsetup
# this is for whom have no idea about simple CI/CD setup
# HERE we need some S/W installations and provisioning them in two of AWS servers! 1)Jenkins SERVER 2) Web Server
 #DEVTEAMmemembers----->>GITREPO------>[JENKINS]GItINTEGRATION====> [MAVEN]INT'TO BUILD,,,,,,,>TomcatSERVER INT' to DEPLOY.
 # PLIGINs for INTEgration{git, maven, deploy to container}    
STEP_1: i am having one server with java jdk installed in it with maven git jenkins configured along with the environment set up for jdk and maven.
##java Installation
    sudo yum install wget -y
    sudo yum install java-1.8* {ENV: cd ~, vi .bashrc, JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.242.b08-0.el7_7.x86_64,        PATH=$PATH:$JAVA_HOME, source .bashrc}
##maven installation
      mkdir /opt/maven
      cd /opt/maven
      sudo wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
      sudo tar -xvzf /opt/apach*
       cd apache*
       {
       sudo nano /etc/profile.d/maven.sh export JAVA_HOME=/usr/lib/jvm/jre-openjdk
export M2_HOME=/opt/maven
export MAVEN_HOME=/opt/maven
export PATH=${M2_HOME}/bin:${PATH}
OR  vi .bashrc
       MAVEN_HOME=/opt/maven/apachemaven
       M2_HOME=$MAVEN_HOME/bin
       PATH=$M2_HOME/bin:$PATH
       source .bashrc
 ##git installation
        yum install -y git
 ##TOMCAT INSTALLATION
        Wget  http://apache.mirror.gtcomm.net/tomcat/tomcat-7/v7.0.100/bin/apache-tomcat-7.0.100.tar.gz
        tar -xvzf apache-tomcat-7.0.100.tar.gz
        cd apache-tomcat-7.0.100/bin
        chmod +x /bin/startup.sh
        chmod +x /bin/shutdown.sh
        ln -s /opt/tomcat/apache-tomcat-7.0.100/bin/shutdown.sh /usr/local/bin/tomcatdown
        ln -s /opt/tomcat/apache-tomcat-7.0.100/bin/startup.sh /usr/local/bin/tomcatup
        vi ./conf/server.xml>>>>>replace as per ur need>>>>>connector port=”8089”
        vi /conf/tomcat-users.xml
        <role rolename="manager-gui"/>
                <role rolename="manager-script"/>
                <role rolename="manager-jmx"/>
                <role rolename="manager-status"/>
                <user username="admin" password="admin123" roles="manager-gui, manager-script, manager-jmx, manager-status"/>
                 <user username="deployer" password="deployer" roles="manager-script"/>
                 <user username="tomcat" password="tomcat123" roles="manager-gui"/>

        


