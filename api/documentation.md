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
| Acrab XI | 132 | 3215655918 |
| Charon Prime | 157 | 2007360508 |
| Crimsica | 78 | 1886266372 |
| Elysian Meadows | 98 | 3533355425 |
| Fort Sanctuary | 32 | 3945891756 |
| Freedom Peak | 15 | 3749877391 |
| Gatria | 173 | 1039531899 |
| Gunvald | 108 | 435094671 |
| Ingmar | 155 | 2655630774 |
| Kharst | 54 | 4190033207 |
| Liberty Ridge | 102 | 1017957570 |
| Overgoe Prime | 213 | 2798506372 |
| Providence | 23 | 1257502272 |
| Stout | 236 | 3478070727 |
| Ubanea | 241 | 2216912817 |
| Valgaard | 73 | 3238002446 |
| Valmox | 90 | 1922612740 |
| Yed Prior | 250 | 714233297 |

## Other biomes

| Biome | Planet name | Index | Hash |
| :--- | :--- | :---: | :---: |
| Swamp | Asperoth Prime | 143 | 770159872 |
| Swamp | Bore Rock | 124 | 2435651414 |
| Swamp | Barabos | 43 | 1678797801 |
| Swamp | Caph | 150 | 3480296110 |
| Swamp | Clasa | 162 | 4171074231 |
| Acidic Desert | Botein | 145 | 784275392 |
| Acidic Desert | Charbal-VII | 156 | 3531149629 |
| Acidic Desert | Chort Bay | 160 | 2695598028 |
| Acidic Desert | Darius II | 128 | 2658926073 |
| Acidic Desert | Darrowsport | 8 | 3550298780 |

_____

## Sectors documentation

## Altus sector

Sector index: 1

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Klen Dahth II | 1 | 3621417917 |
| Pathfinder V | 2 | 2543303604 |
| Widow's Harbor | 3 | 2768073863 |
| New Haven | 4 | 158585041 |
| Pilen V | 5 | 1008084099 |

## Barnard sector

Sector index: 2

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Hydrofall Prime | 6 |  |
| Darrowsport | 8 |  |
| Fornskogur II | 9 |  |
| Midasburg | 10 |  |
| Veil | 30 |  |
| Marre IV | 31 |  |

## Cancri sector

Sector index: 3

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Cerberus IIIc | 11 | 688773671 |
| Prosperity Falls | 12 |  |
| Fort Sanctuary | 32 |  |
| Seyshel Beach | 33 |  |
| Effluvia | 35 |  |

## Gothmar sector

Sector index: 4

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Okul IV | 13 |  |
| Solghast | 36 |  |
| Diluvia | 37 |  |

## Cantolus sector

Sector index: 5

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Martyr's Bay | 14 |  |
| Freedom Peak | 15 |  |
| Kelvinor | 17 |  |
| Viridia Prime | 38 |  |
| Obari | 39 |  |

## Idun sector 

Sector index: 6

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Wraith | 18 |  |
| Myradesh | 40 |  |
| Atrama | 41 |  |
| Maw | 63 |  |

## Kelvin sector

Sector index: 7

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Igla | 19 |  |
| New Kiruna | 20 |  |
| Fort Justice | 21 |  |
| Zegema Paradise | 22 |  |
| Emeria | 42 |  |

## Iptus sector

Sector index: 8

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Providence | 23 |  |
| Primordia | 24 |  |
| Krakabos | 47 |  |
| Iridica | 48 |  |
| Ratch | 71 |  |
| Valgaard | 73 |  |

## Celeste sector

Sector index: 9

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Sulfura | 25 |  |
| Nublaria I | 26 |  |
| Krakatwo | 27 |  |
| Ivis | 51 |  |
| Slif | 52 |  |
| Moradesh | 85 |  |

## Korpus sector

Sector index: 10

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Volterra | 28 |  |
| Crucible | 29 |  |
| Caramoor | 53 |  |
| Alta V | 81 |  |
| Inari | 83 |  |

## Marspira sector

Sector index: 18

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Barabos | 43 |  |
| Fenmire | 44 |  |
| Mastia | 45 |  |
| Curia | 66 |  |
| Tarsh | 67 |  |

## Talus sector

Sector index: 19

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Shallus | 46 |  |
| Shelt | 68 |  |
| Imber | 69 |  |
| Gaellivare | 116 |  |

## Orion sector

Sector index: 20

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Fort Union | 16 |  |
| Azterra | 49 |  |
| Terrek | 76 |  |
| Cirrus | 77 |  |
| Heeth | 79 |  |
| Veld | 80 |  |
| Angel's Venture | 127 |  |

## 

Sector index: 

| Planet | Index | Hash |
| :--- | :---: | :---: |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |











odd planets:
- Zed Rugosia, id 7, sector 2 but in Ferris sector
- Hellmire, id 34, sector 3 but in Mirin sector
- Fort union, id 16, sector 5 but in Orion sector
- Azur Secundus, sector 20 but in Sten sector
