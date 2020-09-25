#### Rest API for TODO items   
___   

When making my own application for Rest API I had some problems running the app at first: I got an error message ` SLF4J: Failed to load class "org.slf4j.impl.StaticLoggerBinder". `. So I added a dependency for SLF4J Simple Binding and it was resolved. 


Other then that I did not have any particular issues. 

I chose to mock the database as a list, and use this as persistance because the focus was to create an API. Also because there is no particular business logic I did not create a service layer for this experiment. 

[Repo for experiment 2](https://github.com/JennStro/Rest-API-for-TODO-items)    
