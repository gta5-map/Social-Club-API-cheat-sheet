Awards
======

.. http:get:: /games/gtav/career/AwardsAjax?[nickname=(socialclub_username)&category=(category)&]slot=Freemode

  Gives you information about the earned awards and it's completion statuses.

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/career/AwardsAjax?slot=Freemode&nickname=restlessnarwhal HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/awards.txt>`__:

  .. include:: _static/responses/awards.txt
    :literal:
    :code: html
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query optional socialclub_username: target (Social Club username) to query
                                       defaults to logged in Social Club player
  :query optional category: vehicle category, defaults to ``victory``, allowed categories: ``victory``, ``general``, ``crimes``, ``vehicles``, ``heists``, ``rewards``
