Minigames
=========

Returns information about several minigames. Unfortunately you can't
access the stats of other players, so all the requests below return your
own (the account who authorized the requests) statistics.

Darts
-----

.. http:get:: /games/gtav/api/minigames/sport?minigame=darts&slot=Freemode

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/sport?minigame=darts&slot=Freemode HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/minigames_darts.txt>`__:

  .. include:: _static/responses/minigames_darts.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``

Arm wrestling
-------------

.. http:get:: /games/gtav/api/minigames/sport?minigame=armwrestling&slot=Freemode

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/sport?minigame=armwrestling&slot=Freemode HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/minigames_armwrestling.txt>`__:

  .. include:: _static/responses/minigames_armwrestling.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``

Flight school
-------------

.. http:get:: /games/gtav/api/minigames/sport?minigame=flightschool&slot=Freemode

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/sport?minigame=flightschool&slot=Freemode HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/minigames_flightschool.txt>`__:

  .. include:: _static/responses/minigames_flightschool.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``

Golf
----

.. http:get:: /games/gtav/api/minigames/sport?minigame=golf&slot=Freemode

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/sport?minigame=golf&slot=Freemode HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/minigames_golf.txt>`__:

  .. include:: _static/responses/minigames_golf.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``

Tennis
------

.. http:get:: /games/gtav/api/minigames/sport?minigame=tennis&slot=Freemode

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/api/minigames/sport?minigame=tennis&slot=Freemode HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/minigames_tennis.txt>`__:

  .. include:: _static/responses/minigames_tennis.txt
    :literal:
    :code: json
    :end-line: 30

  :query slot: needs to be ``Freeroam``
