Garage
======

General information
-------------------

::

    GET /gtav/GarageAjax?config=&nickname=<SOCIALCLUB_NAME>&slot=Freemode&gamerHandle=&gamerTag=&category=&_=1419698615779

Shows stats (name, primary color, secondary color, etc.) of the vehicles
in your main (?) garage. Note: The info is hidden in a
``<script></script>``-tag that stored the information as JSON. If you
need more information you can also use the per-car requests.

Detailed information per car
----------------------------

::

    GET /member/[SOCIALCLUB_NAME]/games/gtav/api/garage/gtaonline/[0-9]?_=1419699070436

This will also show additional the specs of the car (acceleration,
handling, braking, etc.) as well as the car lights (Xeon/Non-xeon),
suspension and more. Make sure to replace "[0-9]" with a number between
0 and 9. At the moment I don't know how to access cars from the
different garages.
