Weapons
=======

General statistics
------------------

.. http:get:: /gtav/WeaponsAjax?(nickname=&)slot=Freemode

  Contains information about kill death ratio, headshots, shots fired, drive-by kills and overall accuracy. For detailed information per weapon checkout the detailed information requests below.

  **Example request**:

  .. sourcecode:: http

    GET /gtav/WeaponsAjax?nickname=RestlessNarwhal&slot=Freemode HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/weapons_general.txt>`_:

  .. include:: _static/responses/weapons_general.txt
    :literal:
    :code: html
    :end-line: 30

  Note: Look out for the ``settings.WeaponsJson`` JavaScript object that holds the information!

  :query slot: needs to be ``Freeroam``
  :query optional nickname: target (Social Club name) to query
                            defaults to logged in Social Club player


Per weapon statistics
---------------------

.. http:get:: /member/(socialclub_name)/games/gtav/api/mp/(weapon_category)/0/(weapon_name)

  Returns detailed information for the given weapon such as:

  -  general information: damage, fire rate, accuracy and range
  -  player data: headshots, shots, hits, kills, deaths, body shots and held time

  **Example request**:

  .. sourcecode:: http

    GET /member/restlessnarwhal/games/gtav/api/mp/gun/1/pistol HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/weapons_per-weapon.txt>`_:

  .. include:: _static/responses/weapons_per-weapon.txt
    :literal:
    :code: json
    :end-line: 30

  :query socialclub_name: your Social Club account username
  :query weapon_category: name of the weapon category, see list below
  :query weapon_name: name of the weapon, see list below

Weapon category/names
~~~~~~~~~~~~~~~~~~~~~

To find out the corresponding ``[WEAPON_CATEGORY]`` and
``[WEAPON_NAME]`` you can check the list below:

Gun
^^^

-  ``pistol``
-  ``combat-pistol``
-  ``ap-pistol``
-  ``pistol-50``
-  ``sns-pistol``
-  ``heavy-pistol``
-  ``vintage-pistol``
-  ``marksman-pistol``
-  ``heavy-revolver``
-  ``flare-gun``
-  ``sawed-off-shotgun``
-  ``pump-shotgun``
-  ``assault-shotgun``
-  ``bullpup-shotgun``
-  ``heavy-shotgun``
-  ``double-barrel``
-  ``sweeper-shotgun``
-  ``micro-smg``
-  ``smg``
-  ``assault-smg``
-  ``gusenberg-sweeper``
-  ``machine-pistol``
-  ``mini-smg``
-  ``mg``
-  ``combat-mg``
-  ``assault-rifle``
-  ``carbine-rifle``
-  ``advanced-rifle``
-  ``bullpup-rifle``
-  ``special-carbine``
-  ``compact-rifle``
-  ``compact-rifle``
-  ``sniper-rifle``
-  ``heavy-sniper``
-  ``minigun``

Projectile
^^^^^^^^^^

-  ``grenade-launcher``
-  ``rpg``
-  ``firework-launcher``
-  ``compact-gl``

Thrown
^^^^^^

-  ``grenade``
-  ``sticky-bomb``
-  ``proximity-mine``
-  ``tear-gas``
-  ``molotov``
-  ``pipe-bomb``
-  ``unarmed``

Melee
^^^^^

-  ``knife``
-  ``nightstick``
-  ``hammer``
-  ``baseball-bat``
-  ``crowbar``
-  ``golf-club``
-  ``bottle``
-  ``antique-cavalry-dagger``
-  ``hatchet``
-  ``knuckle-dusters``
-  ``flashlight``
-  ``machete``
-  ``switchblade``
-  ``poolcue``
-  ``wrench``
-  ``battleaxe``
