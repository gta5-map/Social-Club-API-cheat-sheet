Crew
====

.. http:get:: /crew/(crew_name)/games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MostRecent&page=(page_number)

  Returns 20 snapmatic photos. Make sure to increase ``page_number`` to browse through the pagination.

  **Example request**:

  .. sourcecode:: http

    GET /crew/rebl_xb1/games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MostRecent&page=1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/snapmatic_crew.txt>`_:

  .. include:: _static/responses/snapmatic_crew.txt
    :literal:
    :code: json
    :end-line: 30

  :query crew_name: target crew
  :query page_number: page number, starting with ``1``
