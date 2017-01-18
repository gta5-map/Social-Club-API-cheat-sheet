General
=======

Activity counts
---------------

.. http:get:: /jsonp/activitycounts

  Show counter and counts of personal profile activities: crew invites, friend requests, unread private messages and unread notifications.

  **Example request**:

  .. sourcecode:: http

    GET /jsonp/activitycounts HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/general_activity.txt>`__:

  .. include:: _static/responses/general_activity.txt
    :literal:
    :code: json
    :end-line: 30
