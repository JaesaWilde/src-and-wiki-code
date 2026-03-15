# API DOCUMENTATION

## Base info

A planet is defined by a set of values, found in both ```WarStatus.json``` and ```WarInfo.json```.

The data we need for each of the planets is [here](https://api.live.prod.thehelldiversgame.com/api/WarSeason/801/warinfo). Let's take **Klen Dahth II** as an example:

```json
"index": 1,
"settingsHash": 3621417917,
"planetNameId32": 0,
"position":{
  "x": 0.05373042,
  "y": 0.10565466
},
"waypoints": [],
"sector": 1,
"maxHealth": 1000000,
"disabled": false,
"initialOwner": 1
```

Its position on the galactic map is determined by:
- ```"index": 1```
- ```"position": {"x": 0.05373042, "y": 0.10565466}```
- ```"sector": 1```

Its name and biome is determined by:
- ```"settingsHash": 3621417917```

## WarInfo.json

In the ```WarInfo.json``` file, we have to append this data to the ```planetInfos:[]``` section:

```json
"planetInfos":[
         {
          "disabled":false,
          "index":1,
          "initialOwner":1,
          "maxHealth":1000000,
          "position":{
             "x":0.05373042,
             "y":0.10565466
          },
          "sector":1,
          "planetNameId32":0,
          "settingsHash":3621417917,
          "waypoints":[
             
          ]
       }
    ]
```

## WarStatus.json

In the ```WarStatus.json``` file, we have to append this data to the ```planetStatus:[]``` section:

```json
"planetStatus":[
        {
         "health":500000,
         "index":1,
         "owner":1,
         "players":0,
         "position":{
            "x":0.05373042,
            "y":0.10565466
         },
         "regenPerSecond":4.1666665
      }
```

The faction is determined by:
- ```"owner":1```

## Edit the faction

| Value | Faction |
| :---: | :---: |
| ```"owner":1``` | Super Earth |
| ```"owner":2``` | Terminids |
| ```"owner":3``` | Automatons |
| ```"owner":4``` | Illuminate |

## Open the planet

In the ```WarStatus.json``` file, append the following data in the ```"campaigns":[]``` section. Make sure to get the right ```"planetIndex":```.

```json
"campaigns":[
      {
         "count":7,
         "id":1,
         "planetIndex":1,
         "race":1,
         "type":0
      }
   ]
```

## Add a Megacity

You can add a Megacity to any planet. In the  ```WarStatus.json``` file, append the following data in the ```"planetRegions":[]``` section:

```json
"planetRegions":[
      {
         "planetIndex": 1,
         "regionIndex": 0,
         "owner": 4,
         "health": 400000,
         "regerPerSecond": 1.1111112,
         "availabilityFactor": 0,
         "isAvailable": true,
         "players": 0
      }
   ]
```

If you assign a faction to a Megacity on a patch prior to its playability, it will be a classic operation on a Regular or Colony map.
- ```1.003.000```: Illuminate Megacities
- ```1.003.101```: Terminid Megacities
- ```1.003.200```: Automaton Megacities

## Edit the biome

To change the biome (and name) of a planet, change its ```"settingsHash":``` value in the ```WarInfo.json``` file. You can browse this [Planets and Sectors list](https://helldivers.fandom.com/wiki/Planets_and_Sectors?) to grab a planet's index by expanding the "Technical" section of a planet's descriptive box, then refer to the [API data](https://api.live.prod.thehelldiversgame.com/api/WarSeason/801/warinfo) to find the hash.

### Barren Moon

| Planet name | Index | Hash |
| :--- | :---: | :---: |
| Claorell | 161 | 1109752394 |
| Curia | 66 | 1750606702 |
| Dolph | 109 | 2131959183 |
| Fenrir III | 125 | 2875368439 |
| Maia | 195 | 1126502547 |
| Rasp | 86 | 2598991571 |
| RD-4 | 224 | 3659425534 |
| Sirius | 232 | 31903659 |
| Terrek | 76 | 910588397 |
| Widow's Harbor | 3 | 2768073863 |
| Zosma | 252 | 2360232252 |

## Glacial Fjords

| Planet name | Index | Hash |
| :--- | :---: | :---: |
| Alathfar XI | 141 | 1297056046 |
| Arkturus | 74 | 670993741 |
| Borea | 65 | 3293929397 |
| Epsilon Phoencis VI | 167 | 3517952761 |
| Hadar | 176 | 3671746797 |
| Heeth | 79 | 1391690878 |
| Hesoe Prime | 181 | 1581052380 |
| Julheim | 72 | 922433838 |
| Kelvinor | 17 | 2273175182 |
| Marfark | 198 | 2831860380 |
| Mog | 95 | 910436923 |
| New Kiruna | 20 | 1299274778 |
| New Stockholm | 93 | 3515684391 |
| Okul VI | 13 | 2877873656 |
| Vandalon IV | 243 | 230950549 |
| Vega Bay | 246 | 229350423 |
| Vog-Sojoth | 117 | 2580049274 |

## Frozen Boneyard

| Planet name | Index | Hash |
| :--- | :---: | :---: |
| Acrux IX | 133 | 997215371 |
| Choepessa IV | 158 | 2564387350 |
| Deneb Secundus | 164 | 575825411 |
| Estanu | 169 | 356540875 |
| Eukoria | 55 | 3951456049 |
| Grafmere | 92 | 3602852408 |
| Halies Port | 179 | 386932878 |
| Igla | 19 | 768352347 |
| Inari | 83 | 2623879324 |
| Krakatwo | 27 | 2585302931 |
| Lesath | 194 | 3837447591 |
| Martyr's Bay | 14 | 1529228469 |
| Oslo Station | 106 | 1496025116 |
| Stor Tha Prime | 235 | 3339959103 |

## Tundra

| Planet name | Index | Hash |
| :--- | :---: | :---: |
| Andar | 142 | 1526977116 |
| Angel's Venture | 127 | 2003553249 |
| Aurora Bay | 114 | 975759959 |
| Bunda Secundus | 148 | 3228999359 |
| Crucible | 29 | 410562438 |
| Demiurg | 163 | 1270268663 |
| Diluvia | 37 | 760056919 |
| Duma Tyr | 111 | 255676170 |
| Fort Justice | 21 | 3992185257 |
| Ilduna Prime | 62 | 3508592390 |
| Kerth Secundus | 57 | 3674393208 |
| Martale | 199 | 2016899055 |
| Midasburg | 10 | 2767954873 |
| Ras Algethi | 223 | 4053031948 |
| Shelt | 68 | 1223630977 |
| Trandor | 100 | 3515299681 |

## Ionized Grassland

| Planet name | Index | Hash |
| :--- | :---: | :---: |
| Acrab XI | 132 |  |
| Charon Prime | 157 |  |
| Crimsica | 78 |  |
| Elysian Meadows | 98 |  |
| Elysian Meadows | 98 |  |
| Enuliale | 78 |  |
| Fort Sanctuary | 32 |  |
| Freedom Peak | 15 |  |
| Gatria | 173 |  |
| Gunvald | 108 |  |
| Ingmar | 155 |  |
| Kharst | 54 |  |
| Liberty Ridge | 102 |  |
| Overgoe Prime | 213 |  |
| Providence | 23 |  |
| Stout | 236 |  |
| Ubanea | 241 |  |
| Valgaard | 73 |  |
| Valmox | 90 |  |
| Yed Prior | 250 |  |

## Other biomes

| Biome | Planet name | Index | Hash |
| :--- | :--- | :---: | :---: |
| Swamp | Asperoth Prime | 143 |  |
| Swamp | Bore Rock | 124 |  |
| Swamp | Barabos | 43 |  |
| Swamp | Caph | 150 |  |
| Swamp | Clasa | 162 |  |
| Acidic Desert | Botein | 145 |  |
| Acidic Desert | Charbal-VII | 156 |  |
| Acidic Desert | Chort Bay | 160 |  |
| Acidic Desert | Darius II | 128 |  |
| Acidic Desert | Darrowsport | 8 |  |
