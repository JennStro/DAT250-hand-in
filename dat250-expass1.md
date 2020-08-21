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

#### Gitignore 
When making the repository it also made a .gitignore file. Thinking I then was safe, I pushed what I 
had written so far to the repo. But then gitignore files like .xml and .iml also was pushed. I found out that I could use 
`$ git rm --cached path/to/file` to remove files from version control but keep them locally. So I did that, and later found
out that I had two gitignore files: one "proper one" with the correct file-endings to be ignored and one which only had a few. 
So I removed the last one and ensured that all the file-endings were included in the remaining file. Then I pushed my changes, 
and it all sorted out. 

#### Heroku 
I followed the guide to deploy an app with Heroku and deployed the example app. This guide required Java 8 so I installed 
Java 8 using SDKman for this session. I did not have any issues with doing this guide. I managed to run the app both on 
Herokus servers (`heroku open`) and locally (`heroku local web`). Since this was a Maven project I made sure 
 to install all dependencies first by running `mvn clean install`. I also successfully made a new endpoint `/hello` to 
 show the equation (as shown in the guide), and how to link a database to a Heroku app.  

