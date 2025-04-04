
# ak47


	JOURNAL  	 
  IN THE MAJOR COURSE 
              BIG DATA ANALYTICS  
SUBMITTED BY  
      GOVINDA J SHAH 
MSc IT PART I 
FPMSCIT017A 
SEMESTER II
                                UNDER THE GUIDANCE OF  
 Asst. Prof. BEENA KAPADIA  
ACADEMIC YEAR 
2024 – 2025 



 
 
 
This is to certify that Mr. GOVINDA J SHAH of FIRST year M.Sc IT Part I Div.: A, Roll No. FPMSCIT017A of Semester II (2024 - 2025) has successfully completed the Journal for the Major course BIG DATA ANALYTICS as per the guidelines of KES’ Shroff College of Arts and Commerce, Kandivali(W), Mumbai-400067. 
 
Teacher In-charge	 	                   Director 
Asst. Prof. BEENA KAPADIA              Dr. Lily Bhushan               
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 



INDEX 
 
Pr. 
No. 
Title/Aim of The Practical 
Date 
Signature 
 
1 
Implement an application that stores big data in MongoDB and manipulates it using Python. 
04/01/2025 
07/01/2025 
 
2 
Install, configure and run Hadoop and HDFS and explore HDFS on Windows 
16/01/2025 
20/01/2025 
 
3 
Virtual box, Ubuntu and Hadoop Installation 
21/01/2025 
22/01/2025 
 
4 
Implement word count / frequency programs using MapReduce 
25/01/2025 
 
5 
Install and Run Pig then write Pig Latin scripts to load, store, group, aggregate, join, and filter your data. Also execute basic Utility & System Commands. 
13/02/2025 
17/02/2025 
 
6 
Install and Run Hive then use Hive to create database, table, inserting records, fetching records, performing aggregation and string operations. 
10/03/2025 
11/03/2025 



 
 
 
 
 
 
 
 
 
 
 
 
 


PRACTICAL NO. 1 

MONGO DB WITH PYTHON 
 
Aim: Implement an application that stores big data in MongoDB and manipulates it using Python. 
 
Requirements a. PyMongo  
b. Mongo Database  

Step A: Install Mongo database  

Step 1) Go to
(https://www.mongodb.com/download-center/community) and Download  MongoDB Community Server. We will install the 64-bit version for Windows.  



Step 2) Once download is complete open the msi file. Click Next in the start up screen  



Step 3)  1. Accept the End-User License Agreement  2. Click Next  

Step 4) Click on the "complete" button to install all of the components. The custom  option can be used to install selective components or if you want to change the location  of the installation.  



Step 5) Select “Run service as Network Service user”. make a note of the data directory,  we”ll need this later.. Click Next

Step 7) Installation begins. Click Next once completed.  


Step 6) Click on the Install button to start the installation.  


Step 8) Click on the Finish button to complete the installation.  



  
  
  
TEST MONGO DB  

Step 1) Go to " C:\Program Files\MongoDB\Server\4.0\bin" and double click on mongo.exe. Alternatively, you can also click on the MongoDB desktop icon.  
• 	Create the directory where MongoDB will store its files.  
Open command prompt window and apply following commands 
C:\users\admin> cd\  C:\>md data\db  
 
Step 2) Execute mongodb  
Open another command prompt window.  
C:\> cd C:\Program Files\MongoDB\Server\4.0\bin   
C:\Program Files\MongoDB\Server\4.0\bin> mongod  
In case if it gives an error then run the following command:  
C:\Program Files\MongoDB\Server\4.0\bin> mongod –repair  
  

Step 3) Connect to MongoDB using the Mongo shell   Let the MongoDB daemon to run.  
Open another command prompt window and run the following commands:  
C:\users\admin> cd C:\Program Files\MongoDB\Server\4.0\bin  
C:\Program Files\MongoDB\Server\4.0\bin>mongo  
  

Step 4) Install PyMongo  
Open another command prompt window and run the following commands:  
Check the python version on your desktop / laptop and copy that path from window explorer   
C:\users\admin>cd C:\Program Files\Python311\Scripts 
C:\Program Files\<Python38>\Scripts > python -m pip install pymongo  
 
  
Note: # -m option is for <module-name>  Now you have downloaded and installed a mongoDB driver.  
Step 5) Test PyMongo  
Run the following command from python command prompt 
import pymongo  
Now, either create a file in Python IDLE or run all commands one in sequence on Python cell  

Program 1: Creating a Database: create_dp.py  
import pymongo  
myclient = pymongo.MongoClient("mongodb://localhost:27017/")  
mydb = myclient["mybigdata"]  print(myclient.list_database_names())  
  

Progam 2: Creating a Collection:  create_collection.py  
import pymongo  
myclient = pymongo.MongoClient("mongodb://localhost:27017/")  mydb = myclient["mybigdata"]  mycol=mydb["student"]  print(mydb.list_collection_names())  
   

Progam 3: Insert into Collection:  insert_into_collection.py  import pymongo  
myclient = pymongo.MongoClient("mongodb://localhost:27017/")  mydb = myclient["mybigdata"]  mycol=mydb["student"]  
mydict={"name":"Beena", "address":"Mumbai"}  
x=mycol.insert_one(mydict) # insert_one(containing the name(s) and value(s) of each field  
 
Program 4: Insert Multiple data into Collection: insert_many.py  import pymongo  
myclient = pymongo.MongoClient("mongodb://localhost:27017/")  mydb = myclient["mybigdata"]  mycol=mydb["student"]  
mylist=[{"name":"Khyati", "address":"Mumbai"}, {"name":"Kruti", "address":"Mumbai"},  
{"name":"Nidhi", "address":"Pune"}, {"name":"Komal", "address":"Pune"},]  x=mycol.insert_many(mylist)  
 
Step 6) Test in Mongodb to check database and data inserted in collection  
If you want to check your database list, use the command show dbs in mongo  command prompt   
> show dbs  
  
 
If you want to use a database with name mybigdata, then use database  statement would be as follow:   
> use mybigdata  
  
 
If you want to check collection in mongodb use the command show collections  > show collections  
  
 
If you want to display the first row from collection: db.collection_name.find()  > db.student.findOne()  
  
 
If you want to display all the data from collection: db.collection_name.find()  > db.student.find()  
  f. count number of rows in a collection  > db.student.count()  
  
 
Site for R packages documentation: https://cran.r-project.org/web/packages/available_packages_by_name.html 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
PRACTICAL NO. 2 

Hadoop Installation 
 
Aim: Install, configure and run Hadoop and HDFS and explore HDFS on Windows 
 
Steps to Install Hadoop 
Install Java JDK 1.8 
Download Hadoop and extract and place under C drive 
Set Path in Environment Variables 
Config files under Hadoop directory 
Create folder datanode and namenode under data directory 
Edit HDFS and YARN files 
Set Java Home environment in Hadoop environment 
Setup Complete. Test by executing start-all.cmd 

Step 1: Install Java. 1. Create a java folder in C:\ 2. Download and install jdk-8u112-windows-x64 in C:\java and not in c:\program files\java



Step 3.Set the path JAVA_HOME Environment variable. Type env in search window to get environment variable set up window.





Step 2. Download Hadoop 1.Browse the site https://archive.apache.org/dist/hadoop/common/hadoop-2.7.0/ Search for hadoop-2.7.0-src.tar.gz 2.Extract it to c:\ 
3. Rename Hadoop 2.7.0 to Hadoop



Step 4: Set the system path as follows: 








CONFIGURATIONS
Edit file C:/Hadoop/etc/hadoop/core-site.xml, 
paste the xml code in folder and save 
====================================================== 
<configuration> 
<property> 
       <name>fs.defaultFS</name> 
       <value>hdfs://localhost:9000</value> 
 </property> 
</configuration> 
====================================================== 
Rename “mapred-site.xml.template” to “mapred-site.xml” and edit this file C:/Hadoop/etc/hadoop/mapred-site.xml, paste xml code and save this file. 
====================================================== 
<configuration> 
   <property> 
       <name>mapreduce.framework.name</name> 
       <value>yarn</value> 
   </property> 
</configuration> 
 ====================================================== 
Create folder “data” under “C:\Hadoop” 
Create folder “datanode” under “C:\Hadoop\data” Create folder “namenode” under “C:\Hadoop\data” 
 ====================================================== 
Edit file C:\Hadoop\etc\hadoop\hdfs-site.xml, paste xml code and save this file. <configuration> 
<property> 
       <name>dfs.replication</name> 
       <value>1</value> 
   </property> 
 
   <property> 
       <name>dfs.namenode.name.dir</name> 
       <value>/Hadoop/data/namenode</value> 
   </property> 
   <property> 
       <name>dfs.datanode.data.dir</name> 
       <value>/Hadoop/data/datanode</value> 
   </property> 
  </configuration> 
====================================================== 
Edit file C:/Hadoop/etc/hadoop/yarn-site.xml, paste xml code and save this file. <configuration> 
   <property> 
                <name>yarn.nodemanager.aux-services</name> 
                <value>mapreduce_shuffle</value> 
   </property> 
   <property> 
               <name>yarn.nodemanager.auxservices.mapreduce.shuffle.class</name>  
                <value>org.apache.hadoop.mapred.ShuffleHandler</value> 
   </property> 
6. Edit file C:/Hadoop/etc/hadoop/hadoop-env.cmd Find “JAVA_HOME=%JAVA_HOME%” and replace it as  set JAVA_HOME=C:\Java\jdk1.8.0_112 
The image is as follows: 
 
7. 	Hadoop Configurations 
Download bin folder from  https://github.com/s911415/apache-hadoop-3.1.0-winutils 
– Copy the bin folder to c:\Hadoop. Replace the existing bin folder. 

Run winutils file from the bin folder. 
If it shows an error related to any dll file missing then search for it on net and copy that file in c:\windows\system32 folder 
Again run the same file and you will find no error. 

Then Download and run VC_redist.x64.exe 
This is a “redistributable” package of the Visual C runtime code for 64-bit applications, from Microsoft. It contains certain shared code that every application written with Visual C expects to have available on the Windows computer it runs on. 
Format the NameNode 
– Open cmd ‘Run as Administrator’ and type command hdfs namenode –format 
 
11. Testing 
– Open cmd ‘Run as Administrator’ and change directory to C:\Hadoop\sbin 
– type start-all.cmd 
 OR 
 - type start-dfs.cmd 
type start-yarn.cmd 
 
You will get 4 more running threads for Datanode, namenode, resouce manager and node manager 
 
Output: 
Type JPS command to start-all.cmd command prompt, you will get following output. 
 
Run http://localhost:9870/ from any browser 
Or http://localhost:50070/ 
 

 

PRACTICAL NO.3
Virtual Box Installation
  
Aim: Virtual box, Ubuntu and Hadoop Installation 
Step 1: Download and install VirtualBox  
Go to the website of Oracle VirtualBox and get the latest stable version from the following site  https://www.virtualbox.org/ click on ‘Download’’



Step 2:You will get VirtualBox-6.1.22-144080-Win.exe file downloaded.  
Double click and run it. Click on next.




 
Step 3: Click on ‘next’ without changing the default folder as shown below: 


Step 5: Finally, click on ‘Yes’.  


Step 7: It may ask you for the permission to install, click ’yes’ to allow.  
Select ‘Install’ as shown below:



Step 9: Click on ‘Finish’ to finish Installation of virtual box. 



Step 4: Again, click on next as shown below:



Step 6: Click on ’Install’. 


Step 8: You will get the screen as shown below: 





Ubuntu Installation 
 
Download iso file ubuntu-20.04.2.0-desktop-amd64; which is required to install Ubuntu.  
Browse ubuntu.com  
Click on download and 20.04 LTS as shown below:  
LTS stands for Long term support 
 
Step 1: You will get file, which may take few minutes to download.  
Now, click on ‘New’ to virtual box and write Name as ‘Ubuntu’ as shown below:  



Step 3: Here, you allow memory size up to green indicator (1970 MB). Click on ‘Next’. 




Step 2: Click on ‘Next’.  



Step 4: Don’t change anything in this screen and click on ‘Create’. 





Step 5: Click on ‘Next’, keeping the selection as it is (on VDI).’

Step 6: Keep this screen also as it is and click on ‘Next’.



Keep the file location as it is but preferably keep size 100 GB and click on ‘Create’.  
You may see the following screen having Ubuntu on Virtual Machine. 
 
Select ‘settings’  
Select ‘General’ -> ’ Basic’ as shown below:  
You may change the name from Ubuntu to Ubuntu 20.04  Select bidirectional in ‘General’ -> ’ Advanced’ as shown below 

Step 7: Go to ‘System’ option and change the processor up to green bar, usually 4.(if it allows)  

Step 8: and paste your ubuntu .iso file from current folder to C:\Users\ADMIN\VirtualBox VMs\Ubuntu 20.04 folder.  Click on ‘Storage’ and click on ‘Empty’ followed by ‘Choose a disk file’ as shown below: 



Step 9: Browse the folder where you have selected ubuntu iso file


Step 11: Again, click on ‘Start’ button. It will show you the following screen. 


Step 12: Keep on closing all warnings.  
Next you will get following screen automatically. 


Step 10: Click on Ubuntu….iso file and click on open and then click on ok.  Click on Ubuntu -> start button. 



Step 12: And simultaneously one more screen as follows: 





 
Select language -> English and click on ‘Install Ubuntu’.in ‘Keyboard Layout’  screen,  select ‘English US. Click on ‘Continue’. Click on ‘Continue’.  
(if by mistake you select ‘English UK’, then some key will be changed as follows: 
**Note:  
Some Keys for Ubuntu under UK keyboard layout 
“ -> @ 
@ -> “ 
pipe -> take from this file or on google search for pipe in linux ~ -> pipe 
)  
Step 2: Click on ‘continue’


Step 4: Click on continue after entering name, company name, username, password and confirm your password. 


Installation of Ubuntu started. Click on finish once installation done.  
Click on restart and press Enter key. 


Step 1: Select the checkbox for third party software as shown below: 






Step 3: Select Erase disk and Install Ubuntu and click on ‘Install Now’.  
Click on ‘Continue’ on the next screen.  
Select “Kolkata” for “where are you?” and click on ‘Continue’. 









Hadoop Installation  
Prerequisites 
Java Installation: Hadoop requires Java. Install the Java Development Kit (JDK). 
sudo apt update sudo apt install default-jdk java -version 
Hadoop Download: Download Hadoop from the Apache Hadoop website. 
wget https://downloads.apache.org/hadoop/common/hadoop-x.y.z/hadoop-x.y.z.tar.gz tar -xvzf hadoop-x.y.z.tar.gz mv hadoop-x.y.z /usr/local/Hadoop 
Environment Variables: Add Hadoop and Java paths to .bashrc. 
export JAVA_HOME=/usr/lib/jvm/default-java export HADOOP_HOME=/usr/local/hadoop 
export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin export HADOOP_CONF_DIR=$HADOOP_HOME/etc/hadoop export HADOOP_MAPRED_HOME=$HADOOP_HOME export HADOOP_COMMON_HOME=$HADOOP_HOME export HADOOP_HDFS_HOME=$HADOOP_HOME export HADOOP_YARN_HOME=$HADOOP_HOME 
Apply changes: 
source ~/.bashrc 
 
1. Standalone Mode 
This is the default mode for Hadoop and requires minimal configuration. Suitable for testing. 
Verify Default Configuration: No changes to configuration files are necessary. Ensure Hadoop works out of the box: 
hadoop version 
 
Run a Sample Job: 
hadoop jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-x.y.z.jar wordcount input_dir output_dir 
 
Pseudo-Distributed Mode 
In this mode, Hadoop simulates a distributed environment on a single machine. 
Configure Hadoop: Edit the following files under $HADOOP_HOME/etc/hadoop/: 
core-site.xml: 
<configuration> 
    <property> 
        <name>fs.defaultFS</name> 
        <value>hdfs://localhost:9000</value> 
    </property> 
</configuration> 

hdfs-site.xml: 
<configuration> 
    <property> 
        <name>dfs.replication</name> 
        <value>1</value> 
    </property> 
</configuration> 
 
mapred-site.xml (create if missing): 
<configuration> 
    <property> 
        <name>mapreduce.framework.name</name> 
        <value>yarn</value> 
    </property> 
</configuration> 
 
yarn-site.xml: 
<configuration> 
    <property> 
        <name>yarn.nodemanager.aux-services</name> 
        <value>mapreduce_shuffle</value> 
    </property> 
</configuration> 
 
Format the NameNode: 
hdfs namenode -format 
 
Start Hadoop Services: 
start-dfs.sh 
start-yarn.sh 
 
Verify Hadoop Services: Open the following URLs in your browser: 
NameNode: http://localhost:9870 
ResourceManager: http://localhost:8088 

3. Fully Distributed Mode 
A fully distributed setup requires multiple nodes and proper configuration for cluster management. 
1. Pre-requisites: 
Set up multiple machines with Hadoop installed. 
Configure SSH for password-less login between nodes. 
ssh-keygen -t rsa -P "" ssh-copy-id user@remote-node 
 
Edit Configuration Files: Use the same configuration as in pseudo-distributed mode but update the following: 
core-site.xml: Replace localhost with the NameNode's hostname or IP. 
slaves: List all DataNode hostnames/IPs, one per line. 
 
Distribute Hadoop: Copy the Hadoop directory to all worker nodes. 
scp -r $HADOOP_HOME user@remote-node:/usr/local/hadoop 
 
Start the Cluster: 
On the NameNode: 
start-dfs.sh start-yarn.sh 
1.  • 	Verify: 
NameNode: http://namenode-host:9870 
ResourceManager: http://resourcemanager-host:8088  
PRACTICAL NO. 4 
Implement word count 
 
Aim: Implement word count / frequency programs using MapReduce 
https://codesandbox.io/dashboard/recent Click "+ Create" (top-right corner). 
 
Select Server tab  
Select "Node.js" from the template list 

 
Change the code of index.js to the following code: const text = "hello world hello Hadoop hello Pig"; 
// Split the text into words const words = text.split(/\s+/); 
// Count occurrences of each word const wordCount = words.reduce((countMap, word) => {   countMap[word] = (countMap[word] || 0) + 1;   return countMap; 
}, {}); 
 
// Print the output console.log("Word Count:", wordCount); 

Check the output in terminal window: 










PRACTICAL NO. 5

Aim: Install and Run Pig then write Pig Latin scripts to load, store, group, aggregate, join, and filter your data. Also execute basic Utility & amp, System Commands. 
 
Steps to Install Pig on VMware (Virtual Machine) 
1. Install VMware and Set Up a Virtual Machine 
Download and install VMware Workstation Player (Windows/Linux) or VMware Fusion (Mac). 
Download a Linux ISO (Ubuntu, CentOS, or any preferred distribution). 
Create a new virtual machine in VMware and install Linux. 

i): Download and install VirtualBox 
Go to the website of Oracle VirtualBox and get the latest stable version from the following site https://www.virtualbox.org/ click on ‘Download’’ 


Click on  ‘next’ without changing the default folder as shown below: 

Finally, click on ‘Yes’. 

You will get VirtualBox-6.1.22-144080-Win.exe file downloaded. Double click and run it. Click on next. 



Again, click on next as shown below: 


Click on install



It may ask you for the permission to install, click ’yes’ to allow. Select ‘Install’ as shown below: 


Click on ‘Finish’ to finish Installation of virtual box

You will get the screen as shown below: 


You will get the following screen: 


 
ii): download Ubuntu 
Download iso file ubuntu-20.04.2.0-desktop-amd64.iso;  which is required to install Ubuntu. 
Browse ubuntu.com 
Click on download and 20.04 LTS as shown below: LTS stands for Long term support 
 
 
iii) installing Ubuntu 
You will get file, which may take few minutes to download. 
Now, click on ‘New’ to virtual box and write Name as ‘Ubuntu’ as shown below: 




Here, you allow memory size up to green indicator (1970 MB). Click on ‘Next’. 


Click on ‘Next’, keeping the selection as it is (on VDI).’ 






Click on ‘Next’. 


Don’t change anything in this screen and click on ‘Create’. 


Keep this screen also as it is and click on ‘Next’. 


 
  
Keep the file location as it is but preferably keep size 100 GB and click on ‘Create’. You may see the following screen having Ubuntu on Virtual Machine. 
 
Select ‘settings’ 
Select ‘General’ -> ’ Basic’ as shown below: 
You may change the name from Ubuntu to Ubuntu 20.04 Select bidirectional in ‘General’ -> ’ Advanced’ as shown below: 
 
 
Go to ‘System’ option and change the pr