Statistics
==========

.. http:get:: /games/gtav/StatsAjax?(nickname=&)slot=Freemode

  More detailed statistics of general stuff such as:

  -  Career
  -  Skills
  -  General
  -  Crimes,
  -  Vehicles
  -  Cash
  -  Combat
  -  and weapons

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/StatsAjax?nickname=RestlessNarwhal&slot=Freemode HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/player-overview.txt>`__:

  .. include:: _static/responses/statistics.txt
    :literal:
    :code: html
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query optional nickname: target (Social Club name) to query
                            defaults to logged in Social Club player
