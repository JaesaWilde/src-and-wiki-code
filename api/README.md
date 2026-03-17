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

Check out my documentation on:
- [Planet hashes for speedruns](planet_hashes_speedrun.md).
- Sector and planet IDs.

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

## Gallux sector

Sector index: 11

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Kharst | 54 |  |
| Rasp | 86 |  |
| Bashyr | 87 |  |
| Acubens Prime | 134 |  |
| Adhara | 135 |  |
| Afoyay Bay | 136 |  |

## Morgon sector

Sector index: 12

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Eukoria | 55 |  |
| Myrium | 56 |  |
| Regnus | 88 |  |
| Mog | 95 |  |

## Rictus sector

Sector index: 13

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Kerth Secundus | 57 |  |
| Parsh | 58 |  |
| Valmox | 90 |  |
| Iro | 91 |  |
| Grafmere | 92 |  |
| Oasis | 94 |  |
| Genesis Prime | 95 |  |

## Saleria sector

Sector index: 14

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Reaf | 59 |  |
| Irulta | 60 |  |
| Outpost 32 | 96 |  |
| Calypso | 97 |  |

## Meridian sector

Sector index: 15

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Emorath | 61 |  |
| Ilduna Prime | 62 |  |
| Liberty Ridge | 102 |  |
| Baldrick Prime | 103 |  |

## Sagan sector

Sector index: 17

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Borea | 65 |  |
| Oslo Station | 106 |  |
| Gunvald | 108 |  |

## Nanos sector

Sector index: 31

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Julheim | 72 |  |
| Dolph | 109 |  |
| Bekvam III | 110 |  |
| Duma Tyr | 111 |  |

## Falstaff sector

Sector index: 37

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Esker | 75 |  |
| Erson Sands | 122 |  |
| Socorro III | 123 |  |
| Bore Rock | 124 |  |

## Arturion sector

Sector index: 36

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Arkturus | 74 |  |
| Kirrik | 118 |  |
| Mortax Prime | 119 |  |
| Wilford Station | 120 |  |
| Pioneer II | 121 |  |
| Deneb Secundus | 164 |  |
| Electra Bay | 165 |  |

## Draco sector

Sector index: 21

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Crimsica | 78 |  |
| Estanu | 169 |  |
| Fori Prime | 170 |  |

## Borgus sector

Sector index: 22

| Planet | Index | Hash |
| :--- | :---: | :---: |
| Ursica XI | 82 |  |
| Achird III | 112 |  |
| Darius II | 128 |  |
| Achernar Secundus | 130 |  |

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
- Meridia, id 64, sector 17 but in Celeste sector
- Blistica, id 70, sector 8 but in Gellert sector
