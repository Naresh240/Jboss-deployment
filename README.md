# Jboss-deployment

# Download Zip file:
    cd /opt
    wget https://download.jboss.org/wildfly/18.0.0.Final/wildfly-18.0.0.Final.zip
    unzip wildfly-18.0.0.Final.zip
# Open "standalone.xml" file
    vi /opt/wildfly-18.0.0.Final/standalone/configuration/standalone.xml
    
  ![image](https://user-images.githubusercontent.com/58024415/103283494-b8730a80-49fe-11eb-84b7-ad1474f6fcea.png)

  Need to edit as shown in above image and then save file
  
# Goto bin directory inside "wildfly-18.0.0.Final" directory and run "standalone.sh"
    cd /opt/wildfly-18.0.0.Final/bin
    ./standalone.sh
# Open Port number 8080 with in security group and check in UI
  http://3.85.222.150:8080
  
  ![image](https://user-images.githubusercontent.com/58024415/103283658-31726200-49ff-11eb-92fd-10be9e19cf65.png)
# Deploy Springboot Application:
  Pre-Requisites:
    
    - Install GIT
    - Install Maven
# Clone Springboot application code
    git clone https://github.com/Naresh240/Jboss-deployment.git
    cd Jboss-deployment/mavenwebappdemo/
  Build Artifact:
  
    mvn clean install
  Copy Artifact to "/root/wildfly-18.0.0.Final/standalone/deployments" directory
    
    cp targets/mavewebappdemo-2.0.0-SNAPSHOT.war /opt/wildfly-18.0.0.Final/standalone/deployments
  Check output in UI:
  http://3.85.222.150:8080/mavewebappdemo-2.0.0-SNAPSHOT/
  
  ![image](https://user-images.githubusercontent.com/58024415/103284094-53201900-4a00-11eb-84ca-7be7bdbd231d.png)
