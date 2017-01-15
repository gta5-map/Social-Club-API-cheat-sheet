Overview
========

.. http:get:: /games/gtav/career/overviewAjax?(nickname=&)slot=Freemode

  Display general information of online character:

  -  Rank
  -  RP level
  -  Total playtime
  -  Current bank balance
  -  Active crew
  -  Competitive stats
  -  Cash earned
  -  Criminal records
  -  Favorite weapon
  -  Recent activities

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/career/overviewAjax?nickname=RestlessNarwhal&slot=Freemode HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** ` (full) <_static/responses/player-overview.txt>`_:

  .. include:: _static/responses/player-overview.txt
    :literal:
    :code: html
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query optional nickname: target (Social Club name) to query
                            defaults to logged in Social Club player
