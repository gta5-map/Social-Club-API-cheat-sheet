Hierarchy
=========

.. http:get:: /crewapi/(crew_name)/hierarchy/false?pageSize=(items_per_page)&pageIndex=(page_number)&onlineService=sc

  Returns the crew hierarchy. You have to increment ``pageNumber`` to browse through the pagination.

  **Example request**:

  .. sourcecode:: http

    GET /crewapi/rebl_xb1/hierarchy/false?pageSize=999&pageIndex=0&onlineService=sc HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/crew_hierarchy.txt>`_:

  .. include:: _static/responses/crew_hierarchy.txt
    :literal:
    :code: json
    :end-line: 30

  :query crew_name: target crew name
  :query items_per_page: number of items per page
  :query page_number: page number, starts with ``0``
