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



## Edit the biome



## Add a Megacity
