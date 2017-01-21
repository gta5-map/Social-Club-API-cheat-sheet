Explore crews
=============

List crews
----------

.. http:get:: /crewsapi/SearchCrews?crewType=(crew_type)&openCrewFilter=(open_filter)&systemCrewFilter=(system_filter)

  **Example request**:

  .. sourcecode:: http

    GET /crewsapi/SearchCrews?crewType=thrillSeekers&openCrewFilter=-1&systemCrewFilter=-1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/explore-crews_list.txt>`__:

  .. include:: _static/responses/explore-crews_list.txt
    :literal:
    :code: json
    :end-line: 30

  :query optional crew_type: display only a certain crew type, allowed values:
                             ``open``, ``chatterBoxes``, ``thrillSeekers``, ``rebels``, ``soldiers``, ``allStars`` and empty value (anything)
  :query open_filter: search only open crews, allowed values:
                      ``-1`` for false (open and closed crews),
                      ``1`` for true (only open)
  :query system_filter: display only Rockstar crews, allowed values:
                      ``-1`` for false (only official Rockstar crews),
                      ``1`` for true (also player created crews)

Search crews
------------

.. http:get:: /crewsapi/SearchCrews?searchTerm=(search_term)&crewType=(crew_type)&openCrewFilter=(open_filter)&systemCrewFilter=(system_filter)

  **Example request**:

  .. sourcecode:: http

    GET /crewsapi/SearchCrews?searchTerm=rebl&crewType=thrillSeekers&openCrewFilter=1&systemCrewFilter=-1 HTTP/1.1
    Host: socialclub.rockstargames.com

  **Example response** `(full) <_static/responses/explore-crews_search.txt>`__:

  .. include:: _static/responses/explore-crews_search.txt
    :literal:
    :code: json
    :end-line: 30

  :query search_term: The term you want to look for
  :query optional crew_type: display only a certain crew type, allowed values:
                             ``open``, ``chatterBoxes``, ``thrillSeekers``, ``rebels``, ``soldiers``, ``allStars`` and empty value (anything)
  :query open_filter: search only open crews, allowed values:
                      ``-1`` for false (open and closed crews),
                      ``1`` for true (only open)
  :query system_filter: display only Rockstar crews, allowed values:
                      ``-1`` for false (only official Rockstar crews),
                      ``1`` for true (also player created crews)
