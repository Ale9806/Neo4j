# Neo4j
Neo4j is a native graph database, built from the ground up to leverage not only data but also data relationships. Neo4j connects data as it’s stored, enabling queries never before imagined, at speeds never thought possible.
* Neo4j Basic commands: 
<br>
Creat a new node with  a given  attribute: 

 ```
CREATE (n:person {title:"Alejandro"}) RETURN  n
 ```
 <br>
Visualize nodes: 

 ```
 MATCH (n) RETURN n
 ````

 <br>
Update/set New property to exisitning node: 

 ```
MATCH (n:person {name:"Alejandro"}) SET n.age=34
 ````
