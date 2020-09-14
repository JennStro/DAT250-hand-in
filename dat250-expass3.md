##### Installation and verifying   
The installation and verifying went ok with no problems. The only thing was that I had to install gpg so that I could do the verification. But this was easily done with Homebrew.  
 ![VerifyMongoDb](Screenshots/VerifyMongoDb.png?raw=true)  

#### Experiment 1    
 
Insertion   
![InsertionMongoDb](Screenshots/InsertionMongoDb.png?raw=true)   
   
Updating   
![UpdatePaperMongoDb](Screenshots/UpdatePaperMongoDb.png?raw=true)   
   
![UpdateManyMongoDb](Screenshots/UpdateManyMongoDb.png?raw=true)   

Querying    
![QueryMongoDb](Screenshots/QueryMongoDb.png?raw=true)   
   
![OrQueryMongoDb](Screenshots/OrQueryMongoDb.png?raw=true)   
 
 Replacing     
![ReplaceOneMongoDb](Screenshots/ReplaceOneMongoDb.png?raw=true)   
 
 Deleting   
![DeleteAllMongoDb](Screenshots/DeleteAllMongoDb.png?raw=true)   
   
![DeleteManyMonogDb](Screenshots/DeleteManyMonogDb.png?raw=true)   
   
![DeleteOneConditionMongoDb](Screenshots/DeleteOneConditionMongoDb.png?raw=true)   
 
Bulking   
![BulkReadyMonogDb](Screenshots/BulkReadyMonogDb.png?raw=true)   
   
![BulkWriteMongoDb](Screenshots/BulkWriteMongoDb.png?raw=true)   


#### Experiment 2   

Example 1   
![Mapreduce1](Screenshots/MapReduce1.png?raw=true)   

![MapReduce11](Screenshots/MapReduce11.png?raw=true)   

Example 2   
![MapReduce2](Screenshots/MapReduce2.png?raw=true)   

####My own map - reduce    
I wanted to group the orders by date, to see if there are any specific date with more 
orders than others. If we have many orders one day and very few the other day we may want to 
know it so that we can figure out why and make adjustments. We can see that the day with most orders were at 
20.03.2020 with 3 orders. Also we have three days with only one order, and two days with two orders. 

![OwnReduce](Screenshots/MyOwnReduce.png?raw=true)     
 