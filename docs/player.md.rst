Player
======

::

    GET /member/[SOCIALCLUB_NAME]/games/gtav/snapmatic/ajax/search?SearchQuery=&Filter=MostRecent&page=[X]&_=1419780751971

Returns 20 photos of the given player. Make sure to increase ``page`` to
browse through the pagination.

-  ``[CREW_NAME]`` is the name of the crew
-  ``[X]`` is a number starting from 1
-  ``<SEARCH_TERM>`` is an optional search term, leave empty if you
   don't want to filter
