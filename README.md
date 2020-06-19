# Neo4j
Neo4j is a native graph database, built from the ground up to leverage not only data but also data relationships. Neo4j connects data as it’s stored, enabling queries never before imagined, at speeds never thought possible.
* Neo4j Basic commands: 

## NODES ()

Creat a new node with  a given  atribute: 

 ```
          #label   #properties                           #multiple  atributes
CREATE (n:person {title:"Alejandro"}) RETURN  n    or  CREATE (n:player {title:"Cristaino Ronaldo",team:"Juventus"}) RETURN  n
 ```
 <br>
 Creat  mutilpe nodes with given  atribute (just separeate them with comma): 

 ```  
 # give nodes different labels (a,b)
CREATE (a:person {name:"Anish"}), (b:person {name:"Curtis"})
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


 <br>
Delet all existing node: 

 ```
MATCH (n) DETACH DELETE n    or   match (n) where n.name="Alex" delete n
 ````


 <br>
Delet a node with its attachments : 

 ```
MATCH (n { name: 'Andy' }) DETACH DELETE n
 ````
 
 
 ## EDGES []
 
 <br>
Create edges on existing nodes (OPTION 1) : 

 ```
MATCH (a:person {name:'Alejandro'}) , (b:person {name:'Eduardo'}) MERGE (a)-[r:Same]->(b)
 ````
 

 
Create edges on existing nodes (OPTION 2) : 

 ```
 match (a:person {name:"Alejandro"}),(b:person {name:"Curtis"}) CREATE (a)-[r:friends]->(b)
 ````
 

 
 Create loops on existing nodes : 

 ```
 match (a:person {name:"Alejandro"}),(b:person {name:"Alejandro"}) CREATE (a)-[r:same]>(b)
 ````
