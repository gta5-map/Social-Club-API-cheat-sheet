Garage
======

General information
-------------------

.. http:get:: /gtav/GarageAjax?(nickname=&)slot=Freemode

  Shows stats (name, primary color, secondary color, etc.) of the vehicles in your main (?) garage. Note: The info is hidden in a ``<script></script>``-tag that stored the information as JSON. If you need more information you can also use the per-car requests.

  **Example request**:

  .. sourcecode:: http

    GET /gtav/GarageAjax HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/garage_general.txt>`_:

  .. include:: _static/responses/garage_general.txt
    :literal:
    :code: html
    :end-line: 30

  Note: Look out for the ``settings.VehiclesJson`` JavaScript object that holds the information!

  :query slot: needs to be ``Freeroam``
  :query optional nickname: target (Social Club name) to query
                            defaults to logged in Social Club player

Detailed information per car
----------------------------

.. http:get:: /member/(socialclub_name)/games/gtav/api/garage/gtaonline/(car_id)

  This will also show additional the specs of the car (acceleration, handling, braking, etc.) as well as the car lights (Xeon/Non-xeon), suspension and more. Make sure to replace "[0-9]" with a number between 0 and 9. At the moment I don't know how to access cars from the different garages.

  **Example request**:

  .. sourcecode:: http

    GET /member/restlessnarwhal/games/gtav/api/garage/gtaonline/0 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/garage_per-car.txt>`_:

  .. include:: _static/responses/garage_per-car.txt
    :literal:
    :code: json
    :end-line: 30

  :query socialclub_name: your Social Club account username
  :query car_id: name of the weapon, see list below
