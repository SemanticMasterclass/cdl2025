---
hide:
  - navigation
  - toc
---

# LPG Data File

```
// Art History Knowledge Graph


// Clear existing data (if any)
MATCH (n) DETACH DELETE n;


// Create Movement nodes
INSERT
 (renaissance:Movement {
   name: 'Renaissance',
   hasStartDate: 1401,
   hasEndDate: 1600
 }),
 (cubism:Movement {
   name: 'Cubism',
   hasStartDate: 1900,
   hasEndDate: 1940
 }),
 (expressionism:Movement {
   name: 'Expressionism',
   hasStartDate: 1890,
   hasEndDate: 1910
 });


// INSERT Location nodes
INSERT
 (italy:Country {
   name: 'Italy'
 }),
 (usa:Country {
   name: 'USA'
 }),
 (japan:Country {
   name: 'Japan'
 }),
 (russia:Country {
   name: 'Russia'
 }),
 (france:Country {
   name: 'France'
 }),
 (uk:Country {
   name: 'UK'
 }),
 (germany:Country {
   name: 'Germany'
 }),
 (norway:Country {
   name: 'Norway'
 }),
 (florence:City {
   name: 'Florence'
 }),
 (paris:City {
   name: 'Paris'
 }),
 (milan:City {
   name: 'Milan'
 }),
 (rome:City {
   name: 'Rome'
 }),
 (washington_dc:City {
   name: 'Washington DC'
 }),
 (new_york:City {
   name: 'New York'
 }),
 (tokyo:City {
   name: 'Tokyo'
 }),
 (moscow:City {
   name: 'Moscow'
 }),
 (london:City {
   name: 'London'
 }),
 (liverpool:City {
   name: 'Liverpool'
 }),
 (berlin:City {
   name: 'Berlin'
 }),
 (oslo:City {
   name: 'Oslo'
 }),
 (gallery_of_the_academy_florence:Premises {
   name: 'Gallery of the Academy of Florence'
 }),
 (santa_maria_delle_grazie:Premises {
   name: 'Santa Maria delle Grazie'
 }),
 (uffizi_gallery:Premises {
   name: 'Uffizi Gallery'
 }),
 (galleria_borghese:Premises {
   name: 'Galleria Borghese'
 }),
 (palazzo_farnese:Premises {
   name: 'Palazzo Farnese'
 }),
 (pinacoteca_di_brera:Premises {
   name: 'Pinacoteca di Brera'
 }),
 (national_gallery_of_art:Premises {
   name: 'National Gallery of Art'
 }),
 (metropolitan_museum:Premises {
   name: 'The Metropolitan Museum of Art'
 }),
 (tokyo_national_museum:Premises {
   name: 'Tokyo National Museum'
 }),
 (pushkin_museum:Premises {
   name: 'Pushkin State Museum of Fine Arts'
 }),
 (louvre:Premises {
   name: 'Louvre'
 }),
 (villa_di_castello:Premises {
   name: 'Villa di Castello'
 }),
 (galleria_dellaccademia:Premises {
   name: 'Galleria dell\'Accademia'
 }),
 (whitechapel_art_gallery:Premises {
   name: 'Whitechapel Art Gallery'
 }),
 (tate_gallery:Premises {
   name: 'Tate Gallery'
 }),
 (tate_liverpool:Premises {
   name: 'Tate Liverpool'
 }),
 (tate_modern:Premises {
   name: 'Tate Modern'
 }),
 (unter_den_linden_gallery:Premises {
   name: 'Unter den Linden gallery'
 }),
 (nasjonalgalleriet:Premises {
   name: 'Nasjonalgalleriet'
 }),
 (nasjonalmuseet:Premises {
   name: 'Nasjonalmuseet'
 });


// Create Artist nodes
INSERT
 (leonardo_da_vinci:Artist {
   name: 'Leonardo Da Vinci'
 }),
 (michelangelo:Artist {
   name: 'Michelangelo'
 }),
 (sandro_botticelli:Artist {
   name: 'Sandro Botticelli'
 }),
 (pablo_picasso:Artist {
   name: 'Pablo Picasso'
 }),
 (edvard_munch:Artist {
   name: 'Edvard Munch'
 });


// Create Painting nodes
INSERT
 (mona_lisa:Painting {
   name: 'Mona Lisa',
   hasStartCreationDate: 1503,
   hasEndCreationDate: 1517,
   hasPaintType: 'Oil paint'
 }),
 (the_last_supper:Painting {
   name: 'The Last Supper',
   hasStartCreationDate: 1494,
   hasEndCreationDate: 1498,
   hasPaintType: 'Mural paint'
 }),
 (the_birth_of_venus:Painting {
   name: 'The Birth of Venus',
   hasStartCreationDate: 1484,
   hasEndCreationDate: 1486,
   hasPaintType: 'Tempera'
 }),
 (weeping_woman:Painting {
   name: 'Weeping Woman',
   hasStartCreationDate: 1937,
   hasEndCreationDate: 1937,
   hasPaintType: 'Oil paint'
 }),
 (the_scream:Painting {
   name: 'The Scream',
   hasStartCreationDate: 1893,
   hasEndCreationDate: 1893,
   hasPaintType: 'Oil paint'
 });


// Create Sculpture nodes
INSERT
 (david:Sculpture {
   name: 'David',
   hasStartCreationDate: 1501,
   hasEndCreationDate: 1504,
   hasSculptureMaterial: 'Marble'
 });


// Create Material and Paint Type nodes
INSERT
 (oil_paint:PaintType {
   name: 'Oil paint'
 }),
 (mural_paint:PaintType {
   name: 'Mural paint'
 }),
 (tempera:PaintType {
   name: 'Tempera'
 }),
 (marble:SculptureMaterial {
   name: 'Marble'
 });


// Create Location relationships
MATCH (florence:City {name: 'Florence'}), (italy:Country {name: 'Italy'})
INSERT (florence)-[:isLocatedIn]->(italy);


MATCH (milan:City {name: 'Milan'}), (italy:Country {name: 'Italy'})
INSERT (milan)-[:isLocatedIn]->(italy);


MATCH (rome:City {name: 'Rome'}), (italy:Country {name: 'Italy'})
INSERT (rome)-[:isLocatedIn]->(italy);


MATCH (washington_dc:City {name: 'Washington DC'}), (usa:Country {name: 'USA'})
INSERT (washington_dc)-[:isLocatedIn]->(usa);


MATCH (new_york:City {name: 'New York'}), (usa:Country {name: 'USA'})
INSERT (new_york)-[:isLocatedIn]->(usa);


MATCH (tokyo:City {name: 'Tokyo'}), (japan:Country {name: 'Japan'})
INSERT (tokyo)-[:isLocatedIn]->(japan);


MATCH (moscow:City {name: 'Moscow'}), (russia:Country {name: 'Russia'})
INSERT (moscow)-[:isLocatedIn]->(russia);


MATCH (paris:City {name: 'Paris'}), (france:Country {name: 'France'})
INSERT (paris)-[:isLocatedIn]->(france);


MATCH (london:City {name: 'London'}), (uk:Country {name: 'UK'})
INSERT (london)-[:isLocatedIn]->(uk);


MATCH (liverpool:City {name: 'Liverpool'}), (uk:Country {name: 'UK'})
INSERT (liverpool)-[:isLocatedIn]->(uk);


MATCH (berlin:City {name: 'Berlin'}), (germany:Country {name: 'Germany'})
INSERT (berlin)-[:isLocatedIn]->(germany);


MATCH (oslo:City {name: 'Oslo'}), (norway:Country {name: 'Norway'})
INSERT (oslo)-[:isLocatedIn]->(norway);


// Create Premises relationships
MATCH (gallery_of_the_academy_florence:Premises {name: 'Gallery of the Academy of Florence'}),
     (florence:City {name: 'Florence'})
INSERT (gallery_of_the_academy_florence)-[:isLocatedIn]->(florence);


MATCH (santa_maria_delle_grazie:Premises {name: 'Santa Maria delle Grazie'}),
     (milan:City {name: 'Milan'})
INSERT (santa_maria_delle_grazie)-[:isLocatedIn]->(milan);


MATCH (uffizi_gallery:Premises {name: 'Uffizi Gallery'}),
     (florence:City {name: 'Florence'})
INSERT (uffizi_gallery)-[:isLocatedIn]->(florence);


MATCH (galleria_borghese:Premises {name: 'Galleria Borghese'}),
     (rome:City {name: 'Rome'})
INSERT (galleria_borghese)-[:isLocatedIn]->(rome);


MATCH (palazzo_farnese:Premises {name: 'Palazzo Farnese'}),
     (rome:City {name: 'Rome'})
INSERT (palazzo_farnese)-[:isLocatedIn]->(rome);


MATCH (pinacoteca_di_brera:Premises {name: 'Pinacoteca di Brera'}),
     (milan:City {name: 'Milan'})
INSERT (pinacoteca_di_brera)-[:isLocatedIn]->(milan);


MATCH (national_gallery_of_art:Premises {name: 'National Gallery of Art'}),
     (washington_dc:City {name: 'Washington DC'})
INSERT (national_gallery_of_art)-[:isLocatedIn]->(washington_dc);


MATCH (metropolitan_museum:Premises {name: 'The Metropolitan Museum of Art'}),
     (new_york:City {name: 'New York'})
INSERT (metropolitan_museum)-[:isLocatedIn]->(new_york);


MATCH (tokyo_national_museum:Premises {name: 'Tokyo National Museum'}),
     (tokyo:City {name: 'Tokyo'})
INSERT (tokyo_national_museum)-[:isLocatedIn]->(tokyo);


MATCH (pushkin_museum:Premises {name: 'Pushkin State Museum of Fine Arts'}),
     (moscow:City {name: 'Moscow'})
INSERT (pushkin_museum)-[:isLocatedIn]->(moscow);


MATCH (louvre:Premises {name: 'Louvre'}),
     (paris:City {name: 'Paris'})
INSERT (louvre)-[:isLocatedIn]->(paris);


MATCH (villa_di_castello:Premises {name: 'Villa di Castello'}),
     (florence:City {name: 'Florence'})
INSERT (villa_di_castello)-[:isLocatedIn]->(florence);


MATCH (galleria_dellaccademia:Premises {name: 'Galleria dell\'Accademia'}),
     (florence:City {name: 'Florence'})
INSERT (galleria_dellaccademia)-[:isLocatedIn]->(florence);


MATCH (whitechapel_art_gallery:Premises {name: 'Whitechapel Art Gallery'}),
     (london:City {name: 'London'})
INSERT (whitechapel_art_gallery)-[:isLocatedIn]->(london);


MATCH (tate_gallery:Premises {name: 'Tate Gallery'}),
     (london:City {name: 'London'})
INSERT (tate_gallery)-[:isLocatedIn]->(london);


MATCH (tate_liverpool:Premises {name: 'Tate Liverpool'}),
     (liverpool:City {name: 'Liverpool'})
INSERT (tate_liverpool)-[:isLocatedIn]->(liverpool);


MATCH (tate_modern:Premises {name: 'Tate Modern'}),
     (london:City {name: 'London'})
INSERT (tate_modern)-[:isLocatedIn]->(london);


MATCH (unter_den_linden_gallery:Premises {name: 'Unter den Linden gallery'}),
     (berlin:City {name: 'Berlin'})
INSERT (unter_den_linden_gallery)-[:isLocatedIn]->(berlin);


MATCH (nasjonalgalleriet:Premises {name: 'Nasjonalgalleriet'}),
     (oslo:City {name: 'Oslo'})
INSERT (nasjonalgalleriet)-[:isLocatedIn]->(oslo);


MATCH (nasjonalmuseet:Premises {name: 'Nasjonalmuseet'}),
     (oslo:City {name: 'Oslo'})
INSERT (nasjonalmuseet)-[:isLocatedIn]->(oslo);


// Create Artist-Movement relationships
MATCH (leonardo_da_vinci:Artist {name: 'Leonardo Da Vinci'}),
     (renaissance:Movement {name: 'Renaissance'})
INSERT (leonardo_da_vinci)-[:belongsToHistoricalMovement]->(renaissance);


MATCH (michelangelo:Artist {name: 'Michelangelo'}),
     (renaissance:Movement {name: 'Renaissance'})
INSERT (michelangelo)-[:belongsToHistoricalMovement]->(renaissance);


MATCH (sandro_botticelli:Artist {name: 'Sandro Botticelli'}),
     (renaissance:Movement {name: 'Renaissance'})
INSERT (sandro_botticelli)-[:belongsToHistoricalMovement]->(renaissance);


MATCH (pablo_picasso:Artist {name: 'Pablo Picasso'}),
     (cubism:Movement {name: 'Cubism'})
INSERT (pablo_picasso)-[:belongsToHistoricalMovement]->(cubism);


MATCH (edvard_munch:Artist {name: 'Edvard Munch'}),
     (expressionism:Movement {name: 'Expressionism'})
INSERT (edvard_munch)-[:belongsToHistoricalMovement]->(expressionism);


// Create Artist-Artwork relationships
MATCH (leonardo_da_vinci:Artist {name: 'Leonardo Da Vinci'}),
     (mona_lisa:Painting {name: 'Mona Lisa'})
INSERT (leonardo_da_vinci)-[:isArtistOf]->(mona_lisa),
      (mona_lisa)-[:hasArtist]->(leonardo_da_vinci);


MATCH (leonardo_da_vinci:Artist {name: 'Leonardo Da Vinci'}),
     (the_last_supper:Painting {name: 'The Last Supper'})
INSERT (leonardo_da_vinci)-[:isArtistOf]->(the_last_supper),
      (the_last_supper)-[:hasArtist]->(leonardo_da_vinci);


MATCH (michelangelo:Artist {name: 'Michelangelo'}),
     (david:Sculpture {name: 'David'})
INSERT (michelangelo)-[:isArtistOf]->(david),
      (david)-[:hasArtist]->(michelangelo);


MATCH (sandro_botticelli:Artist {name: 'Sandro Botticelli'}),
     (the_birth_of_venus:Painting {name: 'The Birth of Venus'})
INSERT (sandro_botticelli)-[:isArtistOf]->(the_birth_of_venus),
      (the_birth_of_venus)-[:hasArtist]->(sandro_botticelli);


MATCH (pablo_picasso:Artist {name: 'Pablo Picasso'}),
     (weeping_woman:Painting {name: 'Weeping Woman'})
INSERT (pablo_picasso)-[:isArtistOf]->(weeping_woman),
      (weeping_woman)-[:hasArtist]->(pablo_picasso);


MATCH (edvard_munch:Artist {name: 'Edvard Munch'}),
     (the_scream:Painting {name: 'The Scream'})
INSERT (edvard_munch)-[:isArtistOf]->(the_scream),
      (the_scream)-[:hasArtist]->(edvard_munch);


// Create Artwork-Movement relationships
MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (renaissance:Movement {name: 'Renaissance'})
INSERT (mona_lisa)-[:belongsToHistoricalMovement]->(renaissance);


MATCH (the_last_supper:Painting {name: 'The Last Supper'}),
     (renaissance:Movement {name: 'Renaissance'})
INSERT (the_last_supper)-[:belongsToHistoricalMovement]->(renaissance);


MATCH (david:Sculpture {name: 'David'}),
     (renaissance:Movement {name: 'Renaissance'})
INSERT (david)-[:belongsToHistoricalMovement]->(renaissance);


MATCH (the_birth_of_venus:Painting {name: 'The Birth of Venus'}),
     (renaissance:Movement {name: 'Renaissance'})
INSERT (the_birth_of_venus)-[:belongsToHistoricalMovement]->(renaissance);


MATCH (weeping_woman:Painting {name: 'Weeping Woman'}),
     (cubism:Movement {name: 'Cubism'})
INSERT (weeping_woman)-[:belongsToHistoricalMovement]->(cubism);


MATCH (the_scream:Painting {name: 'The Scream'}),
     (expressionism:Movement {name: 'Expressionism'})
INSERT (the_scream)-[:belongsToHistoricalMovement]->(expressionism);


// Create Exhibition relationships
MATCH (david:Sculpture {name: 'David'}),
     (gallery_of_the_academy_florence:Premises {name: 'Gallery of the Academy of Florence'})
INSERT (david)-[:isExhibitedIn]->(gallery_of_the_academy_florence);


// Create David sculpture exhibition relationships with historical dates
MATCH (david:Sculpture {name: 'David'}),
     (villa_di_castello:Premises {name: 'Villa di Castello'})
INSERT (david)-[:isExhibitedIn {
 exhibitStartDate: 1550,
 exhibitEndDate: 1815
}]->(villa_di_castello);


MATCH (david:Sculpture {name: 'David'}),
     (galleria_dellaccademia:Premises {name: 'Galleria dell\'Accademia'})
INSERT (david)-[:isExhibitedIn {
 exhibitStartDate: 1815,
 exhibitEndDate: 1919
}]->(galleria_dellaccademia);


MATCH (david:Sculpture {name: 'David'}),
     (uffizi_gallery:Premises {name: 'Uffizi Gallery'})
INSERT (david)-[:isExhibitedIn {
 exhibitStartDate: 1919,
 exhibitEndDate: 2025
}]->(uffizi_gallery);


MATCH (the_last_supper:Painting {name: 'The Last Supper'}),
     (santa_maria_delle_grazie:Premises {name: 'Santa Maria delle Grazie'})
INSERT (the_last_supper)-[:isExhibitedIn {
 exhibitStartDate: 1498,
 exhibitEndDate: 2025
}]->(santa_maria_delle_grazie);


// Create Birth of Venus exhibition relationships with historical dates
MATCH (the_birth_of_venus:Painting {name: 'The Birth of Venus'}),
     (villa_di_castello:Premises {name: 'Villa di Castello'})
INSERT (the_birth_of_venus)-[:isExhibitedIn {
 exhibitStartDate: 1550,
 exhibitEndDate: 1815
}]->(villa_di_castello);


MATCH (the_birth_of_venus:Painting {name: 'The Birth of Venus'}),
     (galleria_dellaccademia:Premises {name: 'Galleria dell\'Accademia'})
INSERT (the_birth_of_venus)-[:isExhibitedIn {
 exhibitStartDate: 1815,
 exhibitEndDate: 1919
}]->(galleria_dellaccademia);


MATCH (the_birth_of_venus:Painting {name: 'The Birth of Venus'}),
     (uffizi_gallery:Premises {name: 'Uffizi Gallery'})
INSERT (the_birth_of_venus)-[:isExhibitedIn {
 exhibitStartDate: 1919,
 exhibitEndDate: 2025
}]->(uffizi_gallery);


// Create Weeping Woman exhibition relationships with historical dates
MATCH (weeping_woman:Painting {name: 'Weeping Woman'}),
     (whitechapel_art_gallery:Premises {name: 'Whitechapel Art Gallery'})
INSERT (weeping_woman)-[:isExhibitedIn {
 exhibitStartDate: 1939,
 exhibitEndDate: 1939
}]->(whitechapel_art_gallery);


MATCH (weeping_woman:Painting {name: 'Weeping Woman'}),
     (tate_gallery:Premises {name: 'Tate Gallery'})
INSERT (weeping_woman)-[:isExhibitedIn {
 exhibitStartDate: 1960,
 exhibitEndDate: 1960
}]->(tate_gallery);


MATCH (weeping_woman:Painting {name: 'Weeping Woman'}),
     (tate_liverpool:Premises {name: 'Tate Liverpool'})
INSERT (weeping_woman)-[:isExhibitedIn {
 exhibitStartDate: 2010,
 exhibitEndDate: 2010
}]->(tate_liverpool);


MATCH (weeping_woman:Painting {name: 'Weeping Woman'}),
     (tate_modern:Premises {name: 'Tate Modern'})
INSERT (weeping_woman)-[:isExhibitedIn {
 exhibitStartDate: 2024,
 exhibitEndDate: 2025
}]->(tate_modern);


// Create The Scream exhibition relationships with historical dates
MATCH (the_scream:Painting {name: 'The Scream'}),
     (unter_den_linden_gallery:Premises {name: 'Unter den Linden gallery'})
INSERT (the_scream)-[:isExhibitedIn {
 exhibitStartDate: 1893,
 exhibitEndDate: 1893
}]->(unter_den_linden_gallery);


MATCH (the_scream:Painting {name: 'The Scream'}),
     (nasjonalgalleriet:Premises {name: 'Nasjonalgalleriet'})
INSERT (the_scream)-[:isExhibitedIn {
 exhibitStartDate: 1918,
 exhibitEndDate: 1918
}]->(nasjonalgalleriet);


MATCH (the_scream:Painting {name: 'The Scream'}),
     (nasjonalmuseet:Premises {name: 'Nasjonalmuseet'})
INSERT (the_scream)-[:isExhibitedIn {
 exhibitStartDate: 2022,
 exhibitEndDate: 2025
}]->(nasjonalmuseet);


// Create Mona Lisa exhibition relationships with dates
MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (uffizi_gallery:Premises {name: 'Uffizi Gallery'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1913,
 exhibitEndDate: 1913
}]->(uffizi_gallery);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (galleria_borghese:Premises {name: 'Galleria Borghese'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1913,
 exhibitEndDate: 1913
}]->(galleria_borghese);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (palazzo_farnese:Premises {name: 'Palazzo Farnese'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1913,
 exhibitEndDate: 1913
}]->(palazzo_farnese);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (pinacoteca_di_brera:Premises {name: 'Pinacoteca di Brera'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1913,
 exhibitEndDate: 1913
}]->(pinacoteca_di_brera);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (national_gallery_of_art:Premises {name: 'National Gallery of Art'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1963,
 exhibitEndDate: 1963
}]->(national_gallery_of_art);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (metropolitan_museum:Premises {name: 'The Metropolitan Museum of Art'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1963,
 exhibitEndDate: 1963
}]->(metropolitan_museum);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (tokyo_national_museum:Premises {name: 'Tokyo National Museum'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1974,
 exhibitEndDate: 1974
}]->(tokyo_national_museum);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (pushkin_museum:Premises {name: 'Pushkin State Museum of Fine Arts'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1974,
 exhibitEndDate: 1974
}]->(pushkin_museum);


// Create Mona Lisa Louvre exhibition relationships for different periods
MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (louvre:Premises {name: 'Louvre'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1797,
 exhibitEndDate: 1911
}]->(louvre);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (louvre:Premises {name: 'Louvre'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1914,
 exhibitEndDate: 1939
}]->(louvre);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (louvre:Premises {name: 'Louvre'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1947,
 exhibitEndDate: 1962
}]->(louvre);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (louvre:Premises {name: 'Louvre'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1963,
 exhibitEndDate: 1974
}]->(louvre);


MATCH (mona_lisa:Painting {name: 'Mona Lisa'}),
     (louvre:Premises {name: 'Louvre'})
INSERT (mona_lisa)-[:isExhibitedIn {
 exhibitStartDate: 1974,
 exhibitEndDate: 2025
}]->(louvre);


// Money laundering example
// Create Person nodes
INSERT
 (mr_MoneyBags:Person {
   name: 'Mr. MoneyBags'
 }),
 (mrs_MoneyBags:Person {
   name: 'Mrs. MoneyBags'
 });


// Create Company nodes
INSERT
 (blueshell:Company {
   name: 'Blueshell'
 }),
 (foggy_capital:Company {
   name: 'Foggy Capital'
 }),
 (uffizi_gains:Company {
   name: 'Uffizi Gains'
 }),
 (salmon_river_holdings:Company {
   name: 'Salmon River Holdings'
 });


// Create Person-Company relationships
MATCH (mr_MoneyBags:Person {name: 'Mr. MoneyBags'}),
     (blueshell:Company {name: 'Blueshell'})
INSERT (mr_MoneyBags)-[:owns]->(blueshell);


MATCH (mrs_MoneyBags:Person {name: 'Mrs. MoneyBags'}),
     (foggy_capital:Company {name: 'Foggy Capital'})
INSERT (mrs_MoneyBags)-[:owns]->(foggy_capital);


MATCH (blueshell:Company {name: 'Blueshell'}),
     (foggy_capital:Company {name: 'Foggy Capital'})
INSERT (blueshell)-[:owns]->(foggy_capital);


MATCH (blueshell:Company {name: 'Blueshell'}),
     (uffizi_gains:Company {name: 'Uffizi Gains'})
INSERT (blueshell)-[:owns]->(uffizi_gains);


MATCH (blueshell:Company {name: 'Blueshell'}),
     (salmon_river_holdings:Company {name: 'Salmon River Holdings'})
INSERT (blueshell)-[:owns]->(salmon_river_holdings);


// Add Company domicile relationships
MATCH (foggy_capital:Company {name: 'Foggy Capital'}),
     (london:City {name: 'London'})
INSERT (foggy_capital)-[:isDomiciledIn]->(london);


MATCH (uffizi_gains:Company {name: 'Uffizi Gains'}),
     (florence:City {name: 'Florence'})
INSERT (uffizi_gains)-[:isDomiciledIn]->(florence);


MATCH (salmon_river_holdings:Company {name: 'Salmon River Holdings'}),
     (oslo:City {name: 'Oslo'})
INSERT (salmon_river_holdings)-[:isDomiciledIn]->(oslo);


// Create Artwork ownership relationships
MATCH (mr_MoneyBags:Person {name: 'Mr. MoneyBags'}),
     (mona_lisa:Painting {name: 'Mona Lisa'})
INSERT (mr_MoneyBags)-[:owns]->(mona_lisa);


MATCH (foggy_capital:Company {name: 'Foggy Capital'}),
     (weeping_woman:Painting {name: 'Weeping Woman'})
INSERT (foggy_capital)-[:owns]->(weeping_woman);


MATCH (uffizi_gains:Company {name: 'Uffizi Gains'}),
     (david:Sculpture {name: 'David'})
INSERT (uffizi_gains)-[:owns]->(david);


MATCH(salmon_river_holdings:Company {name: 'Salmon River Holdings'}),
     (the_scream:Painting {name: 'The Scream'})
INSERT (salmon_river_holdings)-[:owns]->(the_scream);


// Artefact label for both Paintings and Sculptures
MATCH (a:Painting) SET a:Artefact;
MATCH (a:Sculpture) SET a:Artefact;


// Add isLocatedInCountry property to Premises nodes
MATCH (premises:Premises)-[:isLocatedIn]->(city:City)-[:isLocatedIn]->(country:Country)
INSERT (premises)-[:isLocatedIn]->(country);


// Show everything
MATCH p=()-[]->() RETURN p;
```
