Vehicles
========

General information
-------------------

.. http:get:: /gtav/VehiclesAjax?(nickname=&category=)slot=Freemode

  General information about driven vehicles ingame: fastest speed, amount of stolen vehicles, farthest jump, and more.

  **Example request**:

  .. sourcecode:: http

    GET /gtav/VehiclesAjax HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/vehicles_general.txt>`_:

  .. include:: _static/responses/vehicles_general.txt
    :literal:
    :code: html
    :end-line: 30

  Note: Look out for the ``settings.VehiclesJson`` JavaScript object that holds the information!

  :query slot: needs to be ``Freeroam``
  :query optional nickname: target (Social Club name) to query
                            defaults to logged in Social Club player
  :query optional category: vehicle category, defaults to ``sports``, allowed categories: ``boats``, ``commercial``, ``compacts``, ``coupes``, ``cycles``, ``helicopters``, ``industrial``, ``military``, ``motorcycles``, ``muscle``, ``off-road``, ``planes``, ``sedans``, ``service``, ``sports``, ``sports-classic``, ``super``, ``suvs``, ``utility``, ``vans``

Per vehicle
-----------

.. http:get:: /member/(socialclub_name)/games/gtav/api/gtaonline/(vehicle_category)/(vehicle_name)

  This gives you general information about all the vehicles in the GTA world. Speed, acceleration, amount of seats, if it's a moddable vehicle, if it's storable or sellable, etc.

  (For a full list of categories and vehicle names go to Social Club and navigate to "Vehicles")

  **Example request**:

  .. sourcecode:: http

    GET /member/restlessnarwhal/games/gtav/api/gtaonline/sports/9f HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/vehicles_per-vehicle.txt>`_:

  .. include:: _static/responses/vehicles_per-vehicle.txt
    :literal:
    :code: json
    :end-line: 30

  :query socialclub_name: your Social Club account username
  :query vehicle_category: name of the vehicle category
  :query vehicle_name: name of the vehicle
