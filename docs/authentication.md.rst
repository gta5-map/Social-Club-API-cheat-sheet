Authentication procedure
========================

If you take a look at the login / ``<form>`` element, you'll see a
hidden ``<input>`` tag called "\_\_RequestVerificationToken". This tag
contains a token which is needed for the actual login request -
otherwise Rockstar refuses the authentication, even with proper and
valid credentials.

So initally, you need to make at least three requests to get your hands
on the desired piece of information:

1. Send a *GET request* to "http://socialclub.rockstargames.com/" and
   search for ``__RequestVerificationToken``. Store it's value in a
   variable and the cookie in a cookie jar.

2. Send a *POST request* to
   "https://socialclub.rockstargames.com/profile/signin". Don't forget
   to use the cookie jar from the first request and store the new
   authentication cookie in it as well:

   -  ``login="<SOCIALCLUB_USERNAME>"``
   -  ``password="<SOCIALCLUB_PASS>"``
   -  ``__RequestVerificationToken="<STORED_RVT>"``

3. Since the cookie jar now has a proper authentication cookie, you can
   start parsing the information you need.
