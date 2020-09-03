#### Installing Derby: 

I installed Derby using the manual, but encountered some problems. At first I did not install it in the `/opt/` folder
because I did not think it was specified to be in the opt folder for a reason. Later in the installation
I got an error `ClassNotFound` when verifying Derby. Trying to find out what was wrong, I found out that the opt folder is used for 
holding independent software, so I decided to reinstall Derby to `usr/local/opt` which is the opt folder in mac. 

From then I followed the instructions, and verified the pathnames that was set using `$ echo DERBY_INSTALL` and `$ echo PATHNANE`. 
Also this time I got an error `ClassNotFound` when trying to verify Derby. This time I had not written the full path 
to `$DERBY_INSTALL`, and hence the `$PATHNAME` was wrong. I fixed the variable, run the verify command and got the desired 
output. 

#### Trying out an application   
In Experiment 1 I used the JPAExample given, and after some errors about "not being able to create the database", I found
out that I needed to change the `ij` command given in `persistance.xml` creating the database, to 
`value="jdbc:derby:testDB;create=true"`. Then when I tried to access the database using the application, I got a new error 
saying that the `shema 'TEST' does not exist`. After some looking at the guide on how to set up a project with JPA, I saw that
the command for EclipseLink to create the database was commented out in my project. So I uncommented it to create the DB, 
ran the app and commented it out again so it would not create a new db each time. 

Being a bit more comfortable working with JPA I started from scratch in Experiment 2. I started by creating a Maven project 
and installed all dependencies. I started out with a simple entity "Person" and tried to add i to the database in the main method. 
I then configured the persistance.xml file and ran the app. After getting some error messages I found out that I also needed to install the `derby.shared`
package, so I added this to dependencies. After this I got an error `Language 5 is not supported` or similar, and found out that 
I needed to specify compiler and target properties in maven:    
`<properties> <maven.compiler.source>1.9</maven.compiler.source> <maven.compiler.target>1.9</maven.compiler.target>
</properties>`   

After this I ran the application without any errors, and was able to connect to the database for Intellij as well, using 
DB browser (explained in "Viewing database in Intellij" later). Having added a person successfully to the 
database, I made the other entities as well and defined their relations and their tables. I also realized that when you
 have a child you need to tell JPA to persist this as well when the parent is persisted using `(cascade = CascadeType.PERSIST)`. 
 I was a bit unsure about the relation from Bank to Creditcard, but landed on that it is the "many" side that
 holds the foreign key. Also I added removal where it is possible. For example, when a bank is deleted you want to delete the 
 cards with it, but not the other way around.
 

#### Viewing database in Intellij
I installed the plugin DBNavigator in intellij and then added a custom DB by opening DB Browser and pressing the "+" sign.
Then I configured the connection giving the url, username, password and specify the driver. I needed to give the url `jdbc:derby:` 
followed by the full path name to the database in order to make it work. I got the username and password from the persistance.xml file, 
and the driver library from `/usr/local/opt/Apache/db-derby-10.15.2.0-bin/lib`, and then I chose the "embedded driver" in the drop-down. 
When pressing "Test connection", it succeeded, and I can now view the DB in intellij. 

I had some problems updating this DB Browser when I added data to the database. The data was retrieved from the db correctly 
(was printed out when queried from db), but did not display in the DB browser. I eventually figured out that when updating 
I needed to disconnect from the database and then connect again in DB browser, and sometimes I even had to restart Intellij and
disconnect/connect in order to update the DB browser.

Sometimes when I tried to run main again to add more data to db I got an exception:  
`Failed to start database 'bankdb' with classloader ... ` saying that someone else probably had booted it before. I guess 
this happened because I tried to 'restart database drivers' from DB browser in an attempt to update the DB browser and display
the correct values, because it happened after I had done it. When this error happened I deleted the db and created a new schema 
with the EclipseLink in persistance.xml, and it worked fine afterwards. 

#### Results 

These are the tables that were created:   
![Tables](Screenshots/tables.png?raw=true)   

Table address:   
![Address](Screenshots/Address.png?raw=true)     

Table Bank:   
![Bank](Screenshots/bank.png?raw=true)        
  

Table Credit_Card:   
![Credit_card](Screenshots/creditcard.png?raw=true)       

Table Person:   
![Person](Screenshots/Person.png?raw=true)  

Table Person_address:   
![Person_address](Screenshots/Person_address.png?raw=true)     

Table Person_Credit_Card:   
![Person_credit](Screenshots/Person_Credit_card.png?raw=true)   

Table Pincode:   
![Pincode](Screenshots/Pincode.png?raw=true)         


I created a factory for filling the db with some data to see how it worked. This is the result: 

`select * from ADDRESS`    
![Address_query](Screenshots/Address_query.png?raw=true)      

`select * from BANK`   
![Bank_query](Screenshots/Bank_query.png?raw=true)

`select * from CREDITCARD`      
![Credit_query](Screenshots/creditcard_query.png?raw=true)  

`select * from PERSON_ADDRESS`      
![Person_Address_query](Screenshots/Person_Address_Query.png?raw=true)  

`select * from PERSON_CREDIT_CARD`     
![Person_Credit_query](Screenshots/Person_Creditcard_Query.png?raw=true)  


`select * from PERSON`     
![Person_query](Screenshots/Person_query.png?raw=true)  

`select * from PINCODE`     
![Pin_query](Screenshots/Pincode_Query.png?raw=true)  


#### Links:   

I only did some minor changes to the already given JPA example to do Experiment 1, 
but uploaded the repo anyway:   
Experiment 1:  
https://github.com/JennStro/DAT250-Task-2-Experiment-1   

I wanted to do Experiment 2 "from scratch" now that I felt a bit more comfortable using JPA and 
connecting to the db.    
Experiment 2:    
https://github.com/JennStro/DAT250-tech-experiment-2
 
 

 
 