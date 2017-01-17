Shooting range
==============

Show stats about shooting range challenges.

Hand Guns
---------

.. http:get:: /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=pistols&challenge=(challenge_type)

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=pistols&challenge=random HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/shooting-range_pistols.txt>`_:

  .. include:: _static/responses/shooting-range_pistols.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query minigame: needs to be ``shootingrange``
  :query weapon: needs to be ``pistols``
  :query challenge: target challenge,
                    allowed challenges: ``random``, ``grid`` or ``covered``

Submachine Guns
---------------

.. http:get:: /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=smgs&challenge=(challenge_type)

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=smgs&challenge=random HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/shooting-range_smgs.txt>`_:

  .. include:: _static/responses/shooting-range_smgs.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query minigame: needs to be ``shootingrange``
  :query weapon: needs to be ``smgs``
  :query challenge: target challenge,
                    allowed challenges: ``random``, ``grid`` or ``covered``

Assault Rifles
--------------

.. http:get:: /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=assaultrifles&challenge=(challenge_type)

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=assaultrifles&challenge=random HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/shooting-range_assaultrifles.txt>`_:

  .. include:: _static/responses/shooting-range_assaultrifles.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query minigame: needs to be ``shootingrange``
  :query weapon: needs to be ``assaultrifles``
  :query challenge: target challenge,
                    allowed challenges: ``random``, ``grid`` or ``covered``

Shotguns
--------

.. http:get:: /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=shotguns&challenge=(challenge_type)

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=shotguns&challenge=random HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/shooting-range_shotguns.txt>`_:

  .. include:: _static/responses/shooting-range_shotguns.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query minigame: needs to be ``shootingrange``
  :query weapon: needs to be ``shotguns``
  :query challenge: target challenge,
                    allowed challenges: ``random``, ``grid`` or ``covered``

Light Machine Guns
------------------

.. http:get:: /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=lmgs&challenge=(challenge_type)

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=lmgs&challenge=random HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/shooting-range_lmgs.txt>`_:

  .. include:: _static/responses/shooting-range_lmgs.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query minigame: needs to be ``shootingrange``
  :query weapon: needs to be ``lmgs``
  :query challenge: target challenge,
                    allowed challenges: ``random``, ``grid`` or ``covered``

-  Heavy:

.. http:get:: /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=heavies&challenge=(challenge_type)

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/challenges?minigame=shootingrange&slot=Freemode&weapon=heavies&challenge=random HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/shooting-range_heavies.txt>`_:

  .. include:: _static/responses/shooting-range_heavies.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query minigame: needs to be ``shootingrange``
  :query weapon: needs to be ``heavies``
  :query challenge: target challenge,
                    allowed challenges: ``random``, ``grid`` or ``covered``
