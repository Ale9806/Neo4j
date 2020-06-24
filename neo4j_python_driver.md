 ## Neo4j PYTHON DRIVER
 
 In order to install the Neo4j to your current PYTHON ENVIORMENT just run the follwoing code ( It is importnat that you have neo4j already install in your system if you want to creat a local databas)

 ```
 pip install neo4j
 ````
 As whit every Database in order to acces data we have to follow at least this simple three steps: <br>
1.- Establish Connection to server or local host <br>
2.- Creat a Session <br>
3.- Work with Database<br>
4.- Close conection<br>
<br>
First we have to start  our database from the Neo4j IDE. In order to start your database go to projects, select your database and click on **start**.
<br> If you click on  settings you will notice that  your local host has set 3 different ports:
<br>
* Bolt port 7687 
* HTTP port 7474 
* HTTPs port 7473 
<br>
Since we wll work with python. It is logical that the only port we can acces trhough the driver is: <br>
* Bolt port 7687

### Lets begin our python program: 
* 1.- Import Neo4j and establish Connection with local host through port 7687
``` python 
from neo4j import GraphDatabase
                                                                # User    #Passsword #both set to neo4j unless you changed them 
graph = GraphDatabase.driver(uri="bolt://localhost:7687", auth=("neo4j", "neo4j"))
type(graph) # object check
 ````
 keep in mind that the connection is an object itself. In order to create a session we will have to call this object:
 
2.- Create a Session 
```` python
session =  graph.session()
````
3.- Work with te Database.<br> There are many ways of accesing and working with the database. I found  the follwing way easy to read and understand:

```` python
execute = "MATCH (n) RETURN n" # We create a string containg the exact code we want to execute
nodes = session.run(execute)   # After that we run it with sesssion and store the resulting object
# For this Database we have two nodes so we expect to nodes
for node in nodes:
    print(node[0])   # you can acces the object with a for loop if you wish 
`````

4.- 4.- Close conection
```` python
graph.close()
````

**Congratulations! You now Know how to work with Databases using python's driver for Neo4j**
