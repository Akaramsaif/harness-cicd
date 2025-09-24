# harness-cicd


<img width="1708" height="548" alt="image" src="https://github.com/user-attachments/assets/1e74e377-1010-4db3-a1b4-5874bc6987d5" />




Step to Install the Neo4j database on Ec2 Instance.
Provision an AWS EC2 instance (R5.4xlarge, 100 GB EBS)  
Allow below Security group allows inbound traffic on: 
  Port 7474 (Neo4j HTTP web interface) 
  Port 7687 (Bolt protocol for database connections) 

Download the tarball package using command inside the /opt/neo4j directory.
Connect to the Ec2 instance using SSH.
cd /opt
mkdir neo4j

<img width="1362" height="218" alt="image" src="https://github.com/user-attachments/assets/3cfa4627-aeb2-4e22-b60c-45f974f6513b" />



wget https://dist.neo4j.org/neo4j-enterprise-5.26.6-unix.tar.gz

Extract the file. 
tar -xvzf neo4j-enterprise-5.26.6-unix.tar.gz



Set the Environment Variables 
export NEO4J_HOME=/opt/neo4j 
export PATH=$NEO4J_HOME/bin:$PATH


Edit and update the neo4j.conf file 
vi /opt/neo4j/conf/neo4j.conf

<img width="756" height="167" alt="image" src="https://github.com/user-attachments/assets/77438f9a-14ad-4b55-8234-63d6cb154ec4" />



Start neo4j service  
cd /opt/neo4j 
./bin/neo4j start 
Access Neo4j Database in Browser 






How to enable the GDS & APOC Libraries
 Navigate to below directory and copy the GDS and APOC libraries from products directory to plugins directory.
 <img width="1800" height="258" alt="image" src="https://github.com/user-attachments/assets/394ce528-b33f-4b67-86bb-0f8447673fba" />

 Enabled GDS (Graph Data Science) and APOC (Awesome Procedures On Cypher) plugins by updating the neo4j.conf file with required setting. 
 <img width="1507" height="74" alt="image" src="https://github.com/user-attachments/assets/a03a02c6-0c3c-4f98-8581-e37983b8b2cf" />

Restart the Neo4j Service by using the below command.

./bin/neo4j restart

Installation of Cloud Watch Agent to send the Neo4j database logs to Cloud watch.
What type of Logs it will send- 
  debug logs
  query logs
  neo4j logs
