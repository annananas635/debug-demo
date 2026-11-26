Debugging WS
I denne WS har jeg fundet de 3 fejl ved kører debugmode på Intellij

1- Skibenens retning - Problemet: calculateEndPoint() kaldte getRandomInteger(1) som altid returnerede 0. Derfor blevet skibe kun placeret vandret. Den var løst ved at skrive "getRandomInteger(2)" så der trækkes enten 0 (vandret) eller 1 (lodret)

2- "Ship sunk!" besked - Problemet: Metoden isSunk() tjekkede hitCount > BATTLESHIP_LENGTH. Ved 3 hits evaluerede 3 > 3 til "false". Den var løst ved at ændre operator til hit > = BATTLESHIP_LENGTH

3- ArrayIndexOutOfBoundsException - Problemet: randomGridPoint() genererede startpunkter for tæt på kanten, hvilket fik skibet til at krydse brættets indeksgrænse (indeks10). Her begrænsede max-startpunktet i randomGridPoint() med grid.length - BATTLESHIP_LENGTH 