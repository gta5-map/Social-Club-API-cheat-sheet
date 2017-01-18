"Most recent"
=============

.. http:get:: /games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MostRecent&Page=(page_number)

  Returns 12 of the "most recent" snapmatic photos. Make sure to increase ``page_number`` to browse through the pagination.

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MostRecent&Page=1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/snapmatic_recent.txt>`_:

  .. include:: _static/responses/snapmatic_recent.txt
    :literal:
    :code: json
    :end-line: 30

  :query page_number: page number, starting with ``1``
