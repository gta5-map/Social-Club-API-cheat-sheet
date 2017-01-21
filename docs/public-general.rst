General
=======

Overview
--------

.. http:get:: /games/gtav/career/overviewAjax?(nickname=&)slot=Freemode

  Display general information of online character:

  -  Rank
  -  RP level
  -  Total playtime
  -  Current bank balance
  -  Active crew
  -  Competitive stats
  -  Cash earned
  -  Criminal records
  -  Favorite weapon
  -  Recent activities

  **Example request**:

  .. sourcecode:: http

    GET /games/gtav/career/overviewAjax?nickname=RestlessNarwhal&slot=Freemode HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/public-general_overview.txt>`__:

  .. include:: _static/responses/public-general_overview.txt
    :literal:
    :code: html
    :end-line: 30

  :query slot: needs to be ``Freeroam``
  :query optional nickname: target (Social Club name) to query
                            defaults to logged in Social Club player

Player name to player ID
------------------------

.. http:get:: /member/(socialclub_username)

  For some requests you need to know the player ID instead of the (human readable) player name.

  **Example request**:

  .. sourcecode:: http

    GET /member/restlessnarwhal HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/public-general_name-to-id.txt>`__:

  .. include:: _static/responses/public-general_name-to-id.txt
    :literal:
    :code: html
    :end-line: 30

  :query socialclub_username: target (Social Club name) to query

  Note: Data is hidden somewhere in a ``<script>`` tag (``"uid":36222077``)

Profile feed
------------

.. http:get:: /reference/profilefeed/(socialclub_userid)

  Extract the profile feed from a certain Social Club user. Make sure to find out the ID first.

  **Example request**:

  .. sourcecode:: http

    GET /reference/profilefeed/47990204 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/public-general_profile-feed.txt>`__:

  .. include:: _static/responses/public-general_profile-feed.txt
    :literal:
    :code: json
    :end-line: 30

  :query socialclub_userid: target (Social Club ID) to query

Friends list
------------

.. http:get:: /friends/GetFriendsJson?nickname=(socialclub_name)&pageNumber=(page_number)

  List all friends of a given Social Club username. Lists 12 entries per page.

  **Example request**:

  .. sourcecode:: http

    GET /friends/GetFriendsJson?nickname=restlessnarwhal&pageNumber=0 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/public-general_friends-list.txt>`__:

  .. include:: _static/responses/public-general_friends-list.txt
    :literal:
    :code: json
    :end-line: 30

  :query socialclub_name: target (Social Club username) to query
  :query page_number: page number, starting with ``0``

Search for player
-----------------

.. http:get:: /friends/MemberSearch?searchTerm=(search_term)

  Search for a specific player/username.

  **Example request**:

  .. sourcecode:: http

    GET /friends/MemberSearch?searchTerm=restless HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/public-general_friends-list.txt>`__:

  .. include:: _static/responses/public-general_search-players.txt
    :literal:
    :code: json
    :end-line: 30

  :query search_term: the term you want to search for
