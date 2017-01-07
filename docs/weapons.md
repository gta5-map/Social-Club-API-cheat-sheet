# Weapons 

## General statistics

```
GET /gtav/WeaponsAjax?config=&nickname=<SOCIALCLUB_NAME>&slot=Freemode&gamerHandle=&gamerTag=&_=1419697004841
```

Kill death ratio, headshots, shots fired, drive-by kills and overall accuracy. For detailed information per weapon checkout the detailed information requests below.

## Per weapon statistics

```
GET /member/[SOCIALCLUB_NAME]/games/gtav/api/mp/[WEAPON_CATEGORY]/0/[WEAPON_NAME]?_=1419697066487
```

Returns detailed information for the given weapon such as:

* general information: damage, fire rate, accuracy and range
* player data: headshots, shots, hits, kills, deaths, body shots and held time 

### Weapon category/names  

To find out the corresponding `[WEAPON_CATEGORY]` and `[WEAPON_NAME]` you can check the list below:

#### Gun

- `pistol`
- `combat-pistol`
- `ap-pistol`
- `pistol-50`
- `sns-pistol`
- `heavy-pistol`
- `vintage-pistol`
- `marksman-pistol`
- `heavy-revolver`
- `flare-gun`
- `sawed-off-shotgun`
- `pump-shotgun`
- `assault-shotgun`
- `bullpup-shotgun`
- `heavy-shotgun`
- `double-barrel`
- `sweeper-shotgun`
- `micro-smg`
- `smg`
- `assault-smg`
- `gusenberg-sweeper`
- `machine-pistol`
- `mini-smg`
- `mg`
- `combat-mg`
- `assault-rifle`
- `carbine-rifle`
- `advanced-rifle`
- `bullpup-rifle`
- `special-carbine`
- `compact-rifle`
- `compact-rifle`
- `sniper-rifle`
- `heavy-sniper`
- `minigun`

#### Projectile

- `grenade-launcher`
- `rpg`
- `firework-launcher`
- `compact-gl`

#### Thrown

- `grenade`
- `sticky-bomb`
- `proximity-mine`
- `tear-gas`
- `molotov`
- `pipe-bomb`
- `unarmed`

#### Melee

- `knife`
- `nightstick`
- `hammer`
- `baseball-bat`
- `crowbar`
- `golf-club`
- `bottle`
- `antique-cavalry-dagger`
- `hatchet`
- `knuckle-dusters`
- `flashlight`
- `machete`
- `switchblade`
- `poolcue`
- `wrench`
- `battleaxe`
