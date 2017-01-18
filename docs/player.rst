Player
======

.. http:get:: /member/(nickname)/games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MostRecent&page=(page_number)

  Returns 20 photos of the given player. Make sure to increase ``page`` to browse through the pagination.

  **Example request**:

  .. sourcecode:: http

    GET /gmember/restlessnarwhal/games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MostRecent&page=1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/snapmatic_player.txt>`_:

  .. include:: _static/responses/snapmatic_player.txt
    :literal:
    :code: json
    :end-line: 30

  :query nickname: target player
  :query page_number: page number, starting with ``1``
