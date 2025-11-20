# CYPHER

## Section 0 - Setup Instructions

1. In [Neo4j Sandbox](https://neo4j.com/sandbox/), click the "Launch the Free Sandbox" Button
1. Create an account if you do not already have one
1. Click "+ New Project"
1. In "Select a project", click "Blank Sandbox"
1. Click the "Create and Download credentials" button at the bottom
1. Open this new project
1. Switch Authentication type to "Username / Password"
1. Enter the Username and Password in credentials text file in your downloads folder
1. Copy the entire [data file](https://semanticmasterclass.github.io/cdl2025/lpg_data/) into the top right text box and execute to load all data
1. Enter Cypher queries into the top right text box (e.g. show everything using `MATCH p=()-[]->() RETURN p;`)

## Section 1 - Competency Questions

### Query 1.1

```
MATCH (a:Artefact)-[:hasArtist]->({name:'Leonardo Da Vinci'})
RETURN a.name
```

### Query 1.2

```
MATCH (a:Artefact)-[:belongsToHistoricalMovement]->({name:'Renaissance'})
RETURN a.name
```

### Query 1.3

```
MATCH ({name:'Renaissance'})<-[:belongsToHistoricalMovement]-(a:Artefact)-[:hasArtist]->
    ({name:'Leonardo Da Vinci'})
RETURN a.name
```

## Section 2 - Pattern matching

### Query 2

```
MATCH (p:Person)-[:owns]->{1,}(intermediary:Company)-[:owns]->{0,}(c:Company)
-[:owns]->(art:Artefact),
    	(c)-[:isDomiciledIn]->(domCity:City),
(art)-[e:isExhibitedIn]->(prem:Premises),
		(art)-[e1:isExhibitedIn]->(prem1:Premises)-[:isLocatedIn]->(domCity:City)
WHERE NOT (intermediary)-[:isDomiciledIn]->()
RETURN p.name, c.name, art.name, domCity.name,
    SUM(e1.exhibitEndDate - e1.exhibitStartDate) /
SUM(e.exhibitEndDate - e.exhibitStartDate) > 0.5 AS artwork_exhibit_majority_in_domicile
```

## Section 3 - Path finding

### Query 3.1

```
MATCH p = (:Person)-[:owns]-{1,}(:Person)
RETURN p
```

### Query 3.2

```
MATCH p = (:Company)--{2,4}()
RETURN p, length(p)
```

### Query 3.3

```
MATCH p = (:Person)-[:owns]->()
((c1:Company)-->(c2:Company) WHERE c1.name < c2.name)+
()-[:isDomiciledIn]->()
RETURN p
```

### Query 3.4

```
MATCH dodgyPath = (p:Person)-[:owns]->{1,}(intermediary:Company)-[:owns]->{0,}(c:Company)
-[:owns]->(art:Artefact),
    	(c)-[:isDomiciledIn]->(domCity:City),
(art)-[e:isExhibitedIn]->(prem:Premises),
		(art)-[e1:isExhibitedIn]->(prem1:Premises)-[:isLocatedIn]->(domCity:City)
WHERE NOT (intermediary)-[:isDomiciledIn]->()
RETURN dodgyPath, domCity.name,
    SUM(e1.exhibitEndDate - e1.exhibitStartDate) /
SUM(e.exhibitEndDate - e.exhibitStartDate) > 0.5 AS artwork_exhibit_majority_in_domicile
```
