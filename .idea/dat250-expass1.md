### Report for expass1

#### Downloading JDK 
I downloaded JDK14-Open using SDKman. 

#### IDE and Maven
I have already installed Intellij and Maven. By running `$ mvn -v` I checked that I had the
latest version of Maven installed. 

#### Git
By running `$ git --version` I noticed that I 
have an older version, 2.20.1. So I updated git by using Homebrew and runned 
`$ brew install git`. When I ran `$ git --version` afterwards it had not updated to 2.28.0, so I tried to install it again.
This time I got a message that 2.28.0 was installed, but not linked. So I needed to 
overwrite the old git with the new git. 
So I followed the instructions in the terminal 
and run `brew link git`. Then I got an error that it could not be linked, because the target already existed, so I need 
to delete the old one. I ran `rm '/usr/local/bin/git'` and afterwards `brew link --overwrite git` to link the new git and 
overwrite any conflicting files. Then I opened a new terminal and ran `$ git --version` to check that I got the new version, and
I did.



