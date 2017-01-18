Global snaps
============

.. http:get:: /games/gtav/snapmatic/ajax/search?[SearchQuery=(search_query)&]Filter=(filter)&Page=(page_number)

  You can use this endpoint in case you want to browse through popular snapsmatics or search for a specific term. It'll returns 12 snaps per page. Make sure to increase ``page_number`` to browse through the pagination.

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/snapmatic/ajax/search?Filter=MostRecent&Page=1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/snapmatic_filters.txt>`_:

  .. include:: _static/responses/snapmatic_filters.txt
    :literal:
    :code: json
    :end-line: 30

  :query filter: allowed values: ``mostrecent``, ``trending``, ``popular`` (all-time), ``myfriends``, ``myphotos``, ``mythumbsup``
  :query page_number: page number, starting with ``1``
  :query optional search_query: a specific term to search for
