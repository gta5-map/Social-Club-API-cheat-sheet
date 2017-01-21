Crew snaps
==========

.. http:get:: /crew/(crew_name)/games/gtav/snapmatic/ajax/search?[SearchQuery=(search_query)&]Filter=(filter)&page=(page_number)

  Lists 12 snaps from a specific crew. Make sure to increase ``page_number`` to browse through the pagination.

  **Example request**:

  .. sourcecode:: http

    GET /crew/rebl_xb1/games/gtav/snapmatic/ajax/search?Filter=MostRecent&page=1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/snapmatic_crew.txt>`_:

  .. include:: _static/responses/snapmatic_crew.txt
    :literal:
    :code: json
    :end-line: 30

  :param crew_name: target crew
  :query optional search_query: a specific term to search for
  :query filter: allowed values: ``mostrecent``, ``trending``, ``popular`` (all-time), ``myfriends``, ``myphotos``, ``mythumbsup``
  :query page_number: page number, starting with ``1``
