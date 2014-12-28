Rockstar / R* Social Club "API" cheat sheet
===========================================

In the guide below, you can find some useful informations how to obtain statistics of Social Club profiles, Rockstar's official platform for GTA Online statistics. Either how many times you blew up a police helicopter or how often you died through a jerry can – it's all tracked and viewable online on said platform.

However, it's made for humans to view in the browser and if people decide to build a script or bot to parse the informations, it is rather tricky to obtain the desired piece of information using cURL since the website is using a lot of JavaScript and AJAX to reload stuff in the background. 

In the guide below I will try to describe and collect as many useful informations about the Social Club and it's "API" as possible.

## 1. Table Of Contents

- [1. Table Of Contents](#1-table-of-contents)
- [2. Authentication](#2-authentication)
- [3. Player statistics](#3-player-statistics)
- [3.1. Public](#31-public) 
- [3.1.1 Overview](#311-overview)
- [3.1.2. Statistics](#312-statistics)
- [3.1.3. Weapons](#313-weapons)
- [3.1.3.1. General statistics](#3131-general-statistics)
- [3.1.3.2. Per weapon statistics](#3132-per-weapon-statistics)
- [3.1.4. Garage](#314-garage)
- [3.1.4.1. General informations](#3141-general-informations)
- [3.1.4.2. Detailed informations per car](#3142-detailed-informations-per-car)
- [3.1.5. Vehicles](#315-vehicles)
- [3.1.5.1. General informations](#3151-general-informations)
- [3.1.5.2. Per vehicle](#3152-per-vehicle)
- [3.1.6. Awards](#316-awards)
- [3.2. Private](#32-private)
- [3.2.1. Minigames](#321-minigames)
- [3.2.2. Shooting range](#322-shooting-range)
- [4. Crew statistics](#4-crew-statistics)
- [4.1. Overview](#41-overview)
- [4.1.1. General informations](#411-general-informations)
- [4.1.2. Emblems](#412-emblems)
- [4.1.3. Feuds](#413-feuds)
- [4.1.4. Crew feed](#414-crew-feed)
- [4.2. Members list](#42-members-list)
- [4.3. Hierarchy](#43-hierarchy)
- [4.4. Photos](#44-photos)
- [5. Snapmatic](#5-snapmatic)

## 2. Authentication

Let's begin with the authentication.

If you take a look at the login/`<form>` element, you see a hidden `<input>` tag called "__RequestVerificationToken". This contains a token which is needed in the actual login request otherwise Rockstar refuses the authentication, even with proper credentials.

So basically, you need to make three requests to pass the authentication:

1. _GET_ "`http://socialclub.rockstargames.com/`" and search for "__RequestVerificationToken". Store it's value (something like `coX4ZFyy9nWwi123eZb1OmeJWLQrM7bcAl_nipsz1ih_-hn8123VnGt41F3GzuJgfFj9igjLEeZb9v-DGIjuzsMRP36e3v1238Z-i3KtVo1231IC0`). Also store cookies in a cookie jar.
2. _POST_ the following data to "`https://socialclub.rockstargames.com/profile/signin`" (Don't forget to use the cookie file from the first request as well as store the new authentication cookie in it):
  * `login="<SOCIALCLUB_USERNAME>"`  
  * `password="<SOCIALCLUB_PASS>"`   
  * `__RequestVerificationToken="<STORED_RVT>"`
3. Since now the cookie file has a authentication cookie, you can start parsing the informations you need.

## 3. Player statistics

In this category you can find requests and informations about player statistics. I distinguish between public and private statistics:

* _Public_: informations of any/other player/s
* _Private_: informations only about the player who authenticated the request

Side note: Some of the requests have placeholder or variables inside. Here's a quick legend about them:

* `[PLACEHOLDER]`: This placeholder needs to be replaced or set
* `<PLACEHOLDER>`: Optional placeholder that can be left

### 3.1. Public 

#### 3.1.1 Overview

_Description_: Display general informations about your (or others, if you fill the _nickname_ parameter) online character: 

* rank
* RP level
* total playtime
* current bank balance
* active crew
* competitive stats
* cash earned
* criminal records
* favorite weapon 
* recent activities

_Request URL_:  
`http://socialclub.rockstargames.com/games/gtav/career/overviewAjax?character=Freemode&nickname=<SOCIALCLUB_NAME>&slot=Freemode&gamerHandle=&gamerTag=&_=1419694640015`

_Response format_: HTML

#### 3.1.2. Statistics

_Description_: More detailed statistics of general stuff such as: 

* career
* skills
* general
* crimes,
* vehicles
* cash
* combat
* and weapons

_Request URL_:  
`http://socialclub.rockstargames.com/games/gtav/StatsAjax?character=Freemode&category=&nickname=<SOCIALCLUB_NAME>&slot=Freemode&gamerHandle=&gamerTag=&_=1419696816848`

_Response format_: HTML

#### 3.1.3. Weapons

##### 3.1.3.1. General statistics

_Description_:  Kill death ratio, heatshots, shots fired, drive-by kills and overall accuracy. For detailed informations per weapon checkout the detailed information requests below.

_Request URL_:  
`http://socialclub.rockstargames.com/gtav/WeaponsAjax?config=&nickname=<SOCIALCLUB_NAME>&slot=Freemode&gamerHandle=&gamerTag=&_=1419697004841`

_Response format_: HTML (and JSON hidden in `<script>`-tag)

##### 3.1.3.2. Per weapon statistics

_Description_:  Returns detailed information for the given weapon such as:

* general informations: damage, fire rate, accuracy and range
* player data: headshots, shots, hits, kills, deaths, body shots and held time 

_Request URL_:  
`http://socialclub.rockstargames.com/member/[SOCIALCLUB_NAME]/games/gtav/api/mp/[WEAPON_CATEGORY]/0/[WEAPON_NAME]?_=1419697066487`

_Response format_: JSON

__Weapon category/name table__:  

|gun|projectile|thrown|melee|
|:--|:--|:--|:--|
|pistol|grenade-launcher|grenade|unarmed|
|combat-pistol|rpg|sticky-bomb|knife|
|ap-pistol|firework-launcher|proximity-mine|nightstick|
|pistol-50|homing-launcher|tear-gas|hammer|
|sns-pistol|   |molotov|baseball-bat|
|heavy-pistol|   |   |crowbar|
|vintage-pistol|   |   |golf-club|
|sawed-off-shotgun|   |   |bottle|
|pump-shotgun|   |   |antique-cavalry-dagger|
|assault-shotgun|   |   |hatchet|
|bullpup-shotgun|   |   |   |
|heavy-shotgun|   |   |   |
|micro-smg|   |   |   |
|smg|   |   |   |
|assault-smg|   |   |   |
|gusenberg-sweeper|   |   |   |
|mg|   |   |   |
|combat-mg|   |   |   |
|assault-rifle|   |   |   |
|carbine-rifle|   |   |   |
|advanced-rifle|   |   |   |
|bullpup-rifle|   |   |   |
|special-carbine|   |   |   |
|musket|   |   |   |
|marksman-rifle|   |   |   |
|sniper-rifle|   |   |   |
|heavy-sniper|   |   |   |
|minigun|   |   |   |

__Example__:  

Based on the table above, the request for the "Antique Cavalry Dagger" would be:  

`http://socialclub.rockstargames.com/member/<SOCIALCLUB_NAME>/games/gtav/api/mp/melee/0/antique-cavalry-dagger?_=1419697066487`

#### 3.1.4. Garage

##### 3.1.4.1. General informations

_Description_:  Shows stats (name, primary color, secondary color, etc.) of the vehicles in your main (?) garage. Note: The info is hidden in a `<script></script>`-tag that stored the informations as JSON. If you need more informations you can also use the per-car requests.

_Request URL_:  
`http://socialclub.rockstargames.com/gtav/GarageAjax?config=&nickname=<SOCIALCLUB_NAME>&slot=Freemode&gamerHandle=&gamerTag=&category=&_=1419698615779`

_Response format_: HTML (and JSON hidden in `<script>`-tag)

##### 3.1.4.2. Detailed informations per car

_Description_:  This will also show additional the specs of the car (acceleration, handling, braking, etc.) as well as the car lights (Xeon/Non-xeon), suspension and more. Make sure to replace "[0-9]" with a number between 0 and 9. At the moment I don't know how to access cars from the different garages.

_Request URL_:  
`http://socialclub.rockstargames.com/member/[SOCIALCLUB_NAME]/games/gtav/api/garage/gtaonline/[0-9]?_=1419699070436`

_Response format_: JSON

#### 3.1.5. Vehicles

##### 3.1.5.1. General informations

_Description_:  General informations about driven vehicles ingame: fastest speed, amount of stolen vehicles, farthest jump, and more.

_Request URL_:  
`http://socialclub.rockstargames.com/gtav/VehiclesAjax?config=&nickname=<SOCIALCLUB_NAME>&slot=Freemode&gamerHandle=&gamerTag=&category=&_=1419698615779`

_Response format_: HTML (and JSON hidden in `<script>`-tag)

##### 3.1.5.2. Per vehicle

_Description_:  This gives you general informations about all the vehicles in the GTA world. Speed, acceleration, amount of seats, if it's a moddable vehicle, if it's storable or sellable, etc.

_Request URL_:  
`http://socialclub.rockstargames.com/member/[SOCIALCLUB_NAME]/games/gtav/api/gtaonline/[VEHICLE_CATEGORY]/[VEHICLE_NAME]?_=1419699368973`

_Response format_: JSON

__Example__:

* Obey 9F: `http://socialclub.rockstargames.com/member/[SOCIALCLUB_NAME]/games/gtav/api/gtaonline/sports/9f?_=1419699368973`

(For a full list of categories and names chekout social club and navigate to "Vehicles")

#### 3.1.6. Awards

_Description_:  Gives you information about the earned awards and it's completion statuses.

_Request URL_:  
`http://socialclub.rockstargames.com/games/gtav/career/AwardsAjax?slot=Freemode&nickname=<SOCIALCLUB_NAME>&gamerHandle=&gamerTag=&category=&_=1419699840945`

_Response format_: HTML

### 3.2. Private

#### 3.2.1. Minigames

_Description_:  Returns informations about several minigames. Unfortunately you can't access the stats of other players, so all the requests below return your own (the account who authorized the requests) statistics.

_Request URLs_:  
* Darts:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/sport?minigame=darts&slot=Freemode&_=1419695379474`
* Arm wrestling:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/sport?minigame=armwrestling&slot=Freemode&type=null&_=1419695501121`
* Flight school:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/challenges?minigame=flightschool&slot=Freemode&type=null&_=1419695623773`
* Golf:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/sport?minigame=golf&slot=Freemode&type=null&_=1419704577071`
* Tennis:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/sport?minigame=tennis&slot=Freemode&type=null&_=1419704505656`

_Response format_: JSON

#### 3.2.2. Shooting range

_Description_:  Show stats about shooting range challenges. Make sure to replace __[CHALLENGE_TYPE]__ with one of the available types: 

* random (Random Targets)
* grid (Target Grid)
* covered (Covered Targets)

_Request URLs_:  

* Hand Guns:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&challenge=[CHALLENGE_TYPE]&weapon=pistols&type=null&_=1419695671151`
* Submachine Guns:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&challenge=[CHALLENGE_TYPE]&weapon=smgs&type=null&_=1419695671151`
* Assault Rifles:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&challenge=[CHALLENGE_TYPE]&weapon=assaultrifles&type=null&_=1419695671151`
* Shotguns:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&challenge=[CHALLENGE_TYPE]&weapon=shotguns&type=null&_=1419695671151`
* Light Machine Guns:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&challenge=[CHALLENGE_TYPE]&weapon=lmgs&type=null&_=1419695671151`
* Heavy:  
  `http://socialclub.rockstargames.com/games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&challenge=[CHALLENGE_TYPE]&weapon=heavies&type=null&_=1419695671151`

## 4. Crew statistics

### 4.1. Overview

#### 4.1.1. General informations

_Description_: Shows general informations about the crew, like the crew id which is importent for a bunch of other requests, crew tag, the crew logo, rank titles as well as the permissions. 

_Request URL_:  
`http://socialclub.rockstargames.com/crew/[CREW_NAME]`

_Response format_: HTML (and JSON hidden in `<script>`-tag)

_JSON element_: `SCSettings.dataHead.pnls[0].tplc`

#### 4.1.2. Emblems

_Description_: Returns the emblems and it's image location.

_Request URL_:  
`http://socialclub.rockstargames.com/crew/[CREW_NAME]`

_Response format_: HTML (and JSON hidden in `<script>`-tag)

_JSON element_: `SCSettings.dataBody.pnls[3].tplc`

#### 4.1.3. Feuds

_Description_: Returns the feud statistics

_Request URL_:  
`http://socialclub.rockstargames.com/crew/[CREW_NAME]`

_Response format_: HTML (and JSON hidden in `<script>`-tag)

_JSON element_: `SCSettings.dataBody.pnls[2].tplc`

#### 4.1.4. Crew feed

_Description_: Get the latest crew feed activity. Note: Make sure to set `[CREW_ID]`. How to obtain the crew id is documented in [4.1.1. General informations](#411-general-informations).

_Request URL_:  
`http://socialclub.rockstargames.com/reference/crewfeed/[CREW_ID]?_=1419776423036`

_Response format_: JSON

### 4.2. Members list

_Description_: Returns a part of the member list. You have to increment `pageNumber` to browse through the pagination.

* `[CREW_ID]` can be found in [4.1.1. General informations](#411-general-informations)
* `[X]` is a number starting from 0

_Request URL_:  
`http://socialclub.rockstargames.com/crewsapi/GetMembersList?crewId=[CREW_ID]&pageNumber=[X]&_=1419777577112`

_Response format_: JSON

### 4.3. Hierarchy

_Description_: Returns the crew hierachy.

_Request URL_:  
`http://socialclub.rockstargames.com/crewapi/[CREW_NAME]/hierarchy/1000/false?_=1419777491133`

_Response format_: JSON

### 4.4. Photos

_Description_: Returns 20 snapmatic photos. Make sure to increase `page` to browse through the pagination. 

* `[CREW_NAME]` is the name of the crew  
* `[X]` is a number starting from 1

_Request URL_:  
`http://socialclub.rockstargames.com/crew/[CREW_NAME]/games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MostRecent&page=[X]&_=1419777877377`

_Response format_: JSON

## 5. Snapmatic
