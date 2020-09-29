#### Spring Boot Experiment   

I had some problems with `.gitignore` to ignore the files, because they were already "untracked". So I tried to use `git clean` but this 
also deleted the whole `src/` directory so I ended up opening the spring init project again and create a new repo. Then I 
run `mvn clean install` when I had committed `.gitignore` so that it would detect the files it should 
be ignoring, but there were still some untracked files. I ended up committing all the files and then use 
`git rm -r --cached . ` to get git to forget all the files committed in this commit, but it did not work. 

I did not get the "/hello?name=myName" to work properly, I got the message: `% curl localhost:8080/hello?name=world   
zsh: no matches found: localhost:8080/hello?name=world`
but it workes fine without the requestparameter: ` % curl localhost:8080/hello
  Hello World!%  `, and it worked in the browser.                                                                             


I installed the Spring Commandline Integration using homebrew:    
``$ brew tap pivotal/tap``   
``$ brew install springboot``   
in order to run the Groovy app. 


When trying to run the application with JPA and Derby I got this error: 

``java.lang.IllegalStateException: Failed to execute CommandLineRunner
`` caused by `IdentifierGenerationException: ids for this class must be manually assigned before calling save(): com.example.springbootexperiment.Customer
`   . I eventually found out that this was because I also had ``@Id`` over the getId() in Customer. 


I do get some warnings but the application is running ok.    

[Spring boot experiment](https://github.com/JennStro/spring-boot-experiment.git) 