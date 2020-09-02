##### Installing Derby: 

I installed Derby using the manual, but encountered some problems. At first I did not install it in the `/opt/` folder
because I did not think it was specified to be in the opt folder for a reason. Later in the installation
I got an error `ClassNotFound` when verifying Derby. Trying to find out what was wrong, I found out that the opt folder is used for 
holding independent software, so I decided to reinstall Derby to `usr/local/opt` which is the opt folder in mac. 

From then I followed the instructions, and verified the pathnames that was set using `$ echo DERBY_INSTALL` and `$ echo PATHNANE`. 
Also this time I got an error `ClassNotFound` when trying to verify Derby. This time I had not written the full path 
to `$DERBY_INSTALL`, and hence the `$PATHNAME` was wrong. I fixed the variable, run the verify command and got the desired 
output. 



 
 