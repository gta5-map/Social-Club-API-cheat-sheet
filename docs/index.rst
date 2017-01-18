Rockstar / R* Social Club "API" cheat sheet
===========================================

In the guide below, you can find some useful information how to obtain public statistics of Social Club profiles, Rockstar's official platform for GTA Online statistics. Either how many times you blew up a police helicopter or how often you died through a jerry can – it's all tracked and viewable online on said platform.

Unfortunately, it's only made for humans to look at in the browser and if people want to build a script to parse the information, it is rather tricky to access and parse the desired piece of information using cURL since the website is using lots of JavaScript and AJAX to reload stuff in the background.

In this guide I will try to describe and collect as many useful knowledge about the Social Club and it's "API" as possible.

**Disclaimer**: Using this guide might be a violation of Rockstar's `Terms of Service <http://www.rockstargames.com/legal>`_. I take no responsibility for the way you use it. Any violation of the `TOS <http://www.rockstargames.com/legal>`_ resulting from using this cheat sheet is entirely the user's responsibility.

.. toctree::
   :caption: General

   authentication
   examples

.. toctree::
   :caption: Public player stats

   public-general
   statistics
   weapons
   garage
   vehicles
   awards

.. toctree::
   :caption: Private player stats

   private-general
   minigames
   shooting-range

.. toctree::
   :caption: Crew statistics

   overview
   hierarchy

.. toctree::
   :caption: Snapmatic

   player-snaps
   crew-snaps
   global-snaps
