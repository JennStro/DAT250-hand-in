#### Spring Boot Experiment   

I had some problems with `.gitignore` to ignore the files, because they were already "untracked". So I tried to use `git clean` but this 
also deleted the whole `src/` directory so I ended up opening the spring init project again and create a new repo. Then I 
run `mvn clean install` when I had committed `.gitignore` so that it would detect the files it should 
be ignoring, but there were still some untracked files. I ended up committing all the files and then use 
`git rm -r --cached . ` to get git to forget all the files committed in this commit. Then afterwards when I ran `git status` 
the files to be ignored were no longer "untracked", and I could add the other files to the repo.   


 