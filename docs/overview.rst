Overview
========

General information
-------------------

.. http:get:: /crew/(crew_name)

  Shows general information about the crew, like the *crew ID* which is importent for a bunch of other requests, crew tag, the crew logo, rank titles as well as the permissions.

  **Example request**:

  .. sourcecode:: http

    GET /crew/rebl_xb1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/crew_overview.txt>`_:

  .. include:: _static/responses/crew_overview.txt
    :literal:
    :code: html
    :end-line: 30

  :query crew_name: target crew

Emblems
-------

.. http:get:: /crew/(crew_name)

  Returns the first four crew emblems and it's image location.

  (Caution: data hidden somewhere in ``<script>`` tags)

  **Example request**:

  .. sourcecode:: http

    GET /crew/rebl_xb1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/crew_overview.txt>`_:

  .. include:: _static/responses/crew_overview.txt
    :literal:
    :code: html
    :end-line: 30

  :query crew_name: target crew

Crew feed
---------

.. http:get:: /reference/crewfeed/(crew_id)

  Structured JSON data of all the crew feed messages and events.

  **Example request**:

  .. sourcecode:: http

    GET /reference/crewfeed/20242331 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/crew_feed.txt>`_:

  .. include:: _static/responses/crew_feed.txt
    :literal:
    :code: json
    :end-line: 30

  :query crew_id: target crew ID

Snapmatic pictures
------------------

.. http:get:: /crewapi/(crew_name)/gtav/photo

  Returns the four latest crew snapmatic pictures as well as the total count.

  **Example request**:

  .. sourcecode:: http

    GET /crewapi/rebl_xb1/gtav/photo HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/crew_photo.txt>`_:

  .. include:: _static/responses/crew_photo.txt
    :literal:
    :code: html
    :end-line: 30

  :query crew_name: target crew

Content creator jobs
--------------------

.. http:get:: /crewapi/(crew_name)/gtav/job

  Returns the latest job as well as the total count.

  **Example request**:

  .. sourcecode:: http

    GET /crewapi/rebl_xb1/gtav/job HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/crew_job.txt>`_:

  .. include:: _static/responses/crew_job.txt
    :literal:
    :code: html
    :end-line: 30

  :query crew_name: target crew
