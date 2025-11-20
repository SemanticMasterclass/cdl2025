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
1. Copy the entire [data file](../models/lpg_data.cypher) into the top right text box and execute to load all data
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
MATCH ({name:'Renaissance'})<-[:belongsToHistoricalMovement]-(a:Artefact)-[:hasArtist]->({name:'Leonardo Da Vinci'})
RETURN a.name
```
