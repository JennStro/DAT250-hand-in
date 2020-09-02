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
I started out using the JPAExample given, and after some errors about "not being able to create the database", I found
out that I needed to change the `ij` command given in `persistance.xml` creating the database, to 
`value="jdbc:derby:testDB;create=true"`. Then when I tried to access the database using the application, I got a new error 
saying that the `shema 'TEST' does not exist`. After some looking at the guide on how to set up a project with JPA, I saw that
the command for EclipseLink to create the database was commented out in my project. So I uncommented it to create the DB, 
ran the app and commented it out again so it would not create a new db each time. 


 

 
 