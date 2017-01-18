General
=======

Overview
--------

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

  **Example response** `(full) <_static/responses/public-general_overview.txt>`__:

  .. include:: _static/responses/public-general_overview.txt
    :literal:
    :code: html
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query optional nickname: target (Social Club name) to query
                            defaults to logged in Social Club player

Player name to player ID
------------------------

For some requests you need to know the player ID instead of the (human readable) player name.

.. http:get:: /member/(socialclub_username)

  **Example request**:

  .. sourcecode:: http

    GET /member/restlessnarwhal HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/public-general_name-to-id.txt>`__:

  .. include:: _static/responses/public-general_name-to-id.txt
    :literal:
    :code: html
    :end-line: 30

  :query socialclub_username: target (Social Club name) to query

  Note: Data is hidden somewhere in a ``<script>`` tag (``"uid":36222077``)
