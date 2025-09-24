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


wget https://dist.neo4j.org/neo4j-enterprise-5.26.6-unix.tar.gz

Extract the file. 
tar -xvzf neo4j-enterprise-5.26.6-unix.tar.gz

image-20250923-070331.png


Set the Environment Variables 
export NEO4J_HOME=/opt/neo4j 
export PATH=$NEO4J_HOME/bin:$PATH


Edit and update the neo4j.conf file 
vi /opt/neo4j/conf/neo4j.conf

image-20250923-071229.png


Start neo4j service  
cd /opt/neo4j 
./bin/neo4j start 
Access Neo4j Database in Browser 
