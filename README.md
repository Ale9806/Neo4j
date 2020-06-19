# Neo4j
Neo4j is a native graph database, built from the ground up to leverage not only data but also data relationships. Neo4j connects data as it’s stored, enabling queries never before imagined, at speeds never thought possible.
* Neo4j Basic commands: 
<br>
# NODES

Creat a new node with  a given  atribute: 

 ```
CREATE (n:person {title:"Alejandro"}) RETURN  n
 ```
 <br>
Visualize nodes: 

 ```
 MATCH (n) RETURN n
 ````

 <br>
Update/set New atribute to exisitning node: 

 ```
MATCH (n:person {name:"Alejandro"}) SET n.age=34
 ````

 <br>
Remove atribute of an existing node: 

 ```
MATCH (n:person {name:"Alejandro"}) REMOVE  n.age
 ````
