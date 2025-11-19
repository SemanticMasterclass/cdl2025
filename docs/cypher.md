---
hide:
  - navigation
  - toc
---

# CYPHER

## Section 1 - Competency Questions

### Query 1.1

```
MATCH (a:Painting|Sculpture)-[:hasArtist]->
 ({name:'Leonardo Da Vinci'})
RETURN a.name
```

### Query 1.2

```
MATCH (a:Painting|Sculpture)-[:belongsToHistoricalMovement]->
 ({name:'Renaissance'})
RETURN a.name
```

### Query 1.3

```
MATCH ({name:'Renaissance'})<-[:belongsToHistoricalMovement]-
 (a:Painting|Sculpture)-[:hasArtist]->
 ({name:'Leonardo Da Vinci'})
RETURN a.name
```
