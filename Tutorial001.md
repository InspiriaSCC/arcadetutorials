### @activities true

# MakeCode Arcade: Koble til spillkonsollet
## Introduksjon
### Introduksjon @unplugged

### Steg 1:
Finn en ``||scene:set tilemap to||``-blokk fra Scene-kategorien og plasser den i ``||loops:On Start||``-blokken.
De aller fleste blokkene du skal bruke i denne instruksjonen må ligge inni ``||loops:On Start||``-blokken for å virke.
Du kan alltid klikke på lyspæren for å se hvordan koden din skal se ut. 

```blocks
tiles.setCurrentTilemap(tilemap`level2`)
```
### Steg 2
Klikk på det grå kvadratet i ``||scene:set tilemap to||``-blokken og endre størrelsen på kartet.
Størrelsen endrer du nede i det venstre hjørnet i kart editoren.
Sett størrelsen til 10 ganger 7 som vist på bildet du ser når du klikker på lyspæra.
Klikk på "Done" nederst til høyre når du er ferdig.

![Steg 2](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame01.jpg)

### Steg 3
Nå skal du fylle spillebrettet med gress.
Klikk på det grå kvadratet i ``||scene:set tilemap to||``-blokken.
Finn et grønt kvadrat med gress fra utvalget like over tallene du endret i forrige trinn og klikk på det.
Klikk så på malingsspannet litt lengre opp på siden.
Når du har valgt malingsspannet, klikker du på det store, grårutete bildet midt på skjermen, slik at det fylles med gress.
Trykk på "Done" nederst til høyre når du er ferdig.

![Steg 3](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame02.jpg)
![Steg 3](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame03.jpg)
![Steg 3](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame04.jpg)
![Steg 3](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame05.jpg)

### Steg 4
Nå trenger du en spillfigur. Klikk på ``||sprites:Sprites||``-menyen og hent en ``||sprites:set mySprite to sprite of kind player||``-blokk.
Dra den inn i ``||loops:on start||``-blokken under den forrige blokka.

```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
```

### Steg 5: Velg en spillfigur
Klikk på det grå kvadratet i ``||sprites:set mySprite to sprite of kind player||``-blokken og så på "gallery" øverst midt på siden.
I denne tutorialen har vi valgt å bruke den lille, gule anda. Klikk på figuren du vil ha, og så på "Done" nede til høyre.

![Steg 5](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame06.jpg)
![Steg 5](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame07.jpg)
![Steg 5](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame09.jpg)

### Steg 6
Koden din skal nå se ut omtrent som når du klikker på lyspæra.
Neste trinn blir å plassere anda et tilfeldig sted på skjermen.

```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
```

### Steg 7:
Hent en ``||scene:place mySprite on top of random||``-blokk fra ``||scene:Scene||``-menyen, og plasser den under blokken med spillfiguren din på.

```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
tiles.placeOnRandomTile(mySprite, assets.tile`transparency16`)
```

### Steg 8:
Klikk på det grå kvadratet i ``||scene:place mySprite on top of random||``-blokken og velg ruten med grønt gress.
```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)
```

### Steg 9:
Foreløpig kan du ikke bevege på spillfiguren din. Det må vi fikse.
Hent en ``||move mySprite with buttons||``-blokk fra ``||controller:Controller||``-menyen og sett den inn i koden under den forrige blokken.
Nå kan du flytte på anda ved å bevege på joysticken under konsollsimulatoren på skjermen, eller ved hjelp av piltastene på tastaturet.
Du må kanskje holde musepekeren over konsollsimulatoren for at det skal virke.

```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)
controller.moveSprite(mySprite)
```

### Steg 10:
Nå trenger du en taco som spillfiguren din kan jakte på.
Hent en ``||sprites:set mySprite2 to sprite of kind player||``-blokk fra ``||sprites:Sprites||``-menyen og sett den inn i koden din under forrige blokk.
Endre ``||sprites:kind||`` fra ``||sprites:player||`` til ``||sprites:food||``.
Klikk på det grå kvadratet i ``||sprites:set mySprite2 to sprite of kind player||``-blokken, gå til galleriet og velg den tacoen som har lavest oppløsning.
(Tacoen med høy oppløsning er over dobbelt så stor som anda.)
Klikk på "Done" og gå videre i instruksjonen.

![Steg 5](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame08.jpg)
![Steg 5](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame10.jpg)

### Steg 11:
Koden din skal nå se ut som den du ser når du klikker på lyspæra.

```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)
controller.moveSprite(mySprite)
let mySprite2 = sprites.create(img`
    . . . . . . . e e e e . . . . . 
    . . . . . e e 4 5 5 5 e e . . . 
    . . . . e 4 5 6 2 2 7 6 6 e . . 
    . . . e 5 6 6 7 2 2 6 4 4 4 e . 
    . . e 5 2 2 7 6 6 4 5 5 5 5 4 . 
    . e 5 6 2 2 8 8 5 5 5 5 5 4 5 4 
    . e 5 6 7 7 8 5 4 5 4 5 5 5 5 4 
    e 4 5 8 6 6 5 5 5 5 5 5 4 5 5 4 
    e 5 c e 8 5 5 5 4 5 5 5 5 5 5 4 
    e 5 c c e 5 4 5 5 5 4 5 5 5 e . 
    e 5 c c 5 5 5 5 5 5 5 5 4 e . . 
    e 5 e c 5 4 5 4 5 5 5 e e . . . 
    e 5 e e 5 5 5 5 5 4 e . . . . . 
    4 5 4 e 5 5 5 5 e e . . . . . . 
    . 4 5 4 5 5 4 e . . . . . . . . 
    . . 4 4 e e e . . . . . . . . . 
    `, SpriteKind.Food)
```

### Steg 12:
Det er lurt å få tacoen til å starte på et tilfeldig sted på spillbrettet også. 
Hent en ``||scene:place mySprite on top of random||``-blokk fra ``||scene:Scene||``-menyen og plasser den nederst i koden din.
Endre ``||variables:mySprite||`` til ``||variables:mySprite2||``.
Klikk på det grå kvadratet i blokken og velg den grønne gressruten.

```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)
controller.moveSprite(mySprite)
let mySprite2 = sprites.create(img`
    . . . . . . . e e e e . . . . . 
    . . . . . e e 4 5 5 5 e e . . . 
    . . . . e 4 5 6 2 2 7 6 6 e . . 
    . . . e 5 6 6 7 2 2 6 4 4 4 e . 
    . . e 5 2 2 7 6 6 4 5 5 5 5 4 . 
    . e 5 6 2 2 8 8 5 5 5 5 5 4 5 4 
    . e 5 6 7 7 8 5 4 5 4 5 5 5 5 4 
    e 4 5 8 6 6 5 5 5 5 5 5 4 5 5 4 
    e 5 c e 8 5 5 5 4 5 5 5 5 5 5 4 
    e 5 c c e 5 4 5 5 5 4 5 5 5 e . 
    e 5 c c 5 5 5 5 5 5 5 5 4 e . . 
    e 5 e c 5 4 5 4 5 5 5 e e . . . 
    e 5 e e 5 5 5 5 5 4 e . . . . . 
    4 5 4 e 5 5 5 5 e e . . . . . . 
    . 4 5 4 5 5 4 e . . . . . . . . 
    . . 4 4 e e e . . . . . . . . . 
    `, SpriteKind.Food)
tiles.placeOnRandomTile(mySprite2, sprites.castle.tileGrass1)
```

### Steg 13
Det blir litt for lett å jakte på mat som ligger i ro, så nå skal vi sette fart på tacoen.
Hent en ``||sprites:set mySprite velocity to vx vy||``-blokk fra ``||sprites:Sprites||``-menyen.
Sett den inn nederst i koden din og endre ``||variables:mySprite||`` til ``||variables:mySprite2||``.
```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)
controller.moveSprite(mySprite)
let mySprite2 = sprites.create(img`
    . . . . . . . e e e e . . . . . 
    . . . . . e e 4 5 5 5 e e . . . 
    . . . . e 4 5 6 2 2 7 6 6 e . . 
    . . . e 5 6 6 7 2 2 6 4 4 4 e . 
    . . e 5 2 2 7 6 6 4 5 5 5 5 4 . 
    . e 5 6 2 2 8 8 5 5 5 5 5 4 5 4 
    . e 5 6 7 7 8 5 4 5 4 5 5 5 5 4 
    e 4 5 8 6 6 5 5 5 5 5 5 4 5 5 4 
    e 5 c e 8 5 5 5 4 5 5 5 5 5 5 4 
    e 5 c c e 5 4 5 5 5 4 5 5 5 e . 
    e 5 c c 5 5 5 5 5 5 5 5 4 e . . 
    e 5 e c 5 4 5 4 5 5 5 e e . . . 
    e 5 e e 5 5 5 5 5 4 e . . . . . 
    4 5 4 e 5 5 5 5 e e . . . . . . 
    . 4 5 4 5 5 4 e . . . . . . . . 
    . . 4 4 e e e . . . . . . . . . 
    `, SpriteKind.Food)
tiles.placeOnRandomTile(mySprite2, sprites.castle.tileGrass1)
mySprite2.setVelocity(50, 50)
```

### Steg 14:
Tacoen stopper når den treffer kanten av skjermen.
For å få den til å sprette når den treffer kanten trenger du en ``||sprites:set mySprite bounce on wall||``-blokk.
Hent en i ``||sprites:Sprites||`` menyen og sett den inn nederst i koden din.
Endre ``||variables:mySprite||`` til ``||variables:mySprite2||``, ellers er det anda som spretter, og ikke tacoen.
Pass på at bounce er slått på (on).

```blocks
tiles.setCurrentTilemap(tilemap`level1`)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . b 5 5 b . . . 
    . . . . . . b b b b b b . . . . 
    . . . . . b b 5 5 5 5 5 b . . . 
    . b b b b b 5 5 5 5 5 5 5 b . . 
    . b d 5 b 5 5 5 5 5 5 5 5 b . . 
    . . b 5 5 b 5 d 1 f 5 d 4 f . . 
    . . b d 5 5 b 1 f f 5 4 4 c . . 
    b b d b 5 5 5 d f b 4 4 4 4 b . 
    b d d c d 5 5 b 5 4 4 4 4 4 4 b 
    c d d d c c b 5 5 5 5 5 5 5 b . 
    c b d d d d d 5 5 5 5 5 5 5 b . 
    . c d d d d d d 5 5 5 5 5 d b . 
    . . c b d d d d d 5 5 5 b b . . 
    . . . c c c c c c c c b b . . . 
    `, SpriteKind.Player)
tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)
controller.moveSprite(mySprite)
let mySprite2 = sprites.create(img`
    . . . . . . . e e e e . . . . . 
    . . . . . e e 4 5 5 5 e e . . . 
    . . . . e 4 5 6 2 2 7 6 6 e . . 
    . . . e 5 6 6 7 2 2 6 4 4 4 e . 
    . . e 5 2 2 7 6 6 4 5 5 5 5 4 . 
    . e 5 6 2 2 8 8 5 5 5 5 5 4 5 4 
    . e 5 6 7 7 8 5 4 5 4 5 5 5 5 4 
    e 4 5 8 6 6 5 5 5 5 5 5 4 5 5 4 
    e 5 c e 8 5 5 5 4 5 5 5 5 5 5 4 
    e 5 c c e 5 4 5 5 5 4 5 5 5 e . 
    e 5 c c 5 5 5 5 5 5 5 5 4 e . . 
    e 5 e c 5 4 5 4 5 5 5 e e . . . 
    e 5 e e 5 5 5 5 5 4 e . . . . . 
    4 5 4 e 5 5 5 5 e e . . . . . . 
    . 4 5 4 5 5 4 e . . . . . . . . 
    . . 4 4 e e e . . . . . . . . . 
    `, SpriteKind.Food)
tiles.placeOnRandomTile(mySprite2, sprites.castle.tileGrass1)
mySprite2.setVelocity(50, 50)
mySprite2.setBounceOnWall(true)
```

### Steg 15:
Nå må du gjøre sånn at anda spiser tacoen og får poeng når den tar den.
Til det trenger du en ``||sprites:on sprite of kind Player overlaps otherSprite of kind Player||``-blokk.
Hent en i ``||sprites:Sprites||`` menyen.
Denne blokken skal ligge fritt på arbeidsbordet, og skal ikke legges in i ``||loops:On start||``-blokken.
Endre det siste feltet øverst i blokken slik at ``||variables:otherSprite||`` er av typen ``||sprites:Food||`` og ikke ``||sprites:Player||``.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	
})
```

### Steg 16:
Nå skal du bestemme hva som skjer når anda overlapper tacoen.
Det kuleste er vel om anda spiser tacoen og at det dukker opp en ny taco med det samme?
Hent en ny ``||scene:place mySprite on top of random||`` og plasser den inni ``||sprites:on sprite of kind Player overlaps otherSprite of kind Food||``-blokken.
Endre ``||variables:mySprite||`` til ``||variables:mySprite2||``.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    tiles.placeOnRandomTile(mySprite2, sprites.castle.tileGrass2)
})
```

### Steg 17:
Du må jo få poeng hver gang du fanger en taco!
Hent en ``||info:change score by 1||``-blokk fra ``||info:Info||``-menyen og plasser den nederst i ``||sprites:on sprite of kind Player overlaps otherSprite of kind Food||``-blokken.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    tiles.placeOnRandomTile(mySprite2, sprites.castle.tileGrass2)
    info.changeScoreBy(1)
})
```

### Steg 18:
Nå mangler bare en siste liten detalj.
For å gjøre spillet litt vanskelig, skal vi begrense hvor lang tid du har på å fange tacoer.
Hent en ``||info:start countdown 10 (s)||``-blokk fra ``||info:Info||``-menyen.
Plasser den nederst i ``||loops:On start||``-blokken.
Nå er spillet ferdig! Nå gjenstår det bare å få lastet det ned til spillkonsollet, så kan du teste det ordentlig!
De neste trinnene forklarer hvordan du kobler konsollet til PCen slik at du kan laste ned spillet.

### Steg 19: Koble til spillkonsollet
Om du allerede har koblet til det håndholdte spillkonsollet trenger du ikke å gjøre de neste stegene.
Da kan du bare laste ned koden din og gå ut av denne instruksjonen.
Lek gjerne videre med koden din etterpå, og test ut nye ting.

### Steg 20: Sørg for at konsollet er i tilkoblingsmodus
Før du kan laste ned spillet til konsollet, må du lenke konsollet til PCen.
Da må konsollet være i tilkoblingsmodus.
Om konsollet ser ut som på bildet du ser om du klikker på lyspæra, kan du hoppe over neste punkt.

![Steg 5](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame11.jpg)

### Steg 20
Om bildet så annerledes ut som under lyspæra i forrige trinn, må du trykke på resetknappen under skjermen på konsollet.
Det er den lille, runde knappen til høyre for menyknappen.
Når du har fått trykket på knappen og skjermen ser ut som på bildet som kommer opp når du trykker på lyspæra, kan du gå videre i denne instruksjonen.

![Steg 5](https://raw.githubusercontent.com/InspiriaSCC/arcadetutorials/master/assets/Arcadegame12.jpg)


### Steg 21
Klikk på de tre prikkene ved siden av den oransje ``||Download||``-knappen nede i venstre hjørne på skjermen.
Om menyen som kommer opp ser ut slik som på bildet som kommer frem når du klikker på lyspæra nede til venstre under denne teksten, trenger du ikke å gjøre noe mer.
Da kjenner PCen og MakeCode konsollet fra før, og du kan bare gå ut av denne instruksjonen og trykke på ``||Downlad||`` for å laste ned koden din til konsollet.
Om det ser annerledes ut, følger du instruksjonen videre.
![Tilkobling steg 1](https://raw.githubusercontent.com/InspiriaSCC/energispillet/master/assets/ArcadeConnect2.jpg)
![Tilkobling steg 1](https://raw.githubusercontent.com/InspiriaSCC/energispillet/master/assets/ArcadeConnect3b.jpg)

### Steg 22
Klikk på de tre prikkene ved siden av den oransje ``||Download||``-knappen nede i venstre hjørne på skjermen.
Klikk på <b>Choose hardware</b>.
(Du kan se hvor du skal trykke om du trykker på lyspæren under denne teksten)

![Tilkobling steg 2](https://raw.githubusercontent.com/InspiriaSCC/energispillet/master/assets/ArcadeConnect3.jpg)

### Steg 23
Finn bildet av konsollet du bruker. Konsollet heter "Retro Arcade for Education" og er lyseblått på bildet, akkurat som det du har foran deg.
Klikk på bildet. Når du har gjort det, vet MakeCode Arcade hvilken konsolltype det skal se etter.
![Tilkobling steg 3](https://raw.githubusercontent.com/InspiriaSCC/energispillet/master/assets/ArcadeConnect4.jpg)

### Steg 24
Nå må du hjelpe MakeCode Arkade å finne ditt konsoll på PCen.
Trykk på de tre prikkene ved siden av ``||Download||`` på nytt.
Velg <b>Connect device</b> øverst på listen.
Klikk "Connect device" nede i høyre hjørnet på vinduet som popper opp.
Du får nå opp et vindu med en liste over tilgjengelige konsoller av riktig type.
Klikk først på "Arcade" øverst i listen, så linjen blir blå.
Klikk så på "Koble til". Nå er du koblet til konsollet, og kan laste ned filer direkte ved å klikke på ``||Download||``.
![Tilkobling steg 4](https://raw.githubusercontent.com/InspiriaSCC/energispillet/master/assets/ArcadeConnect5.jpg)
![Tilkobling steg 4](https://raw.githubusercontent.com/InspiriaSCC/energispillet/master/assets/ArcadeConnect6.jpg)
![Tilkobling steg 4](https://raw.githubusercontent.com/InspiriaSCC/energispillet/master/assets/ArcadeConnect7.jpg)



<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
