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
- [Planet biome hashes](planet_biome_hashes.md).
- [Planet coordinates](planet_coordinates.md).
