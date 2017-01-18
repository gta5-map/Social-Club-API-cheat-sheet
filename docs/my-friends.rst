"My friends"
============

.. http:get:: /games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MyFriends&Page=(page_number)

  Returns 12 snaps of the "My friends" category. Make sure to increase ``page_number`` to browse through the pagination.

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MyFriends&Page=1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/snapmatic_friends.txt>`_:

  .. include:: _static/responses/snapmatic_friends.txt
    :literal:
    :code: json
    :end-line: 30

  :query page_number: page number, starting with ``1``
