Authentication procedure
========================

If you take a look at the login / ``<form>`` element, you'll see a hidden ``<input>`` tag called "\_\_RequestVerificationToken". This tag contains a token which is needed for the actual login request - otherwise Rockstar refuses the authentication, even with proper and valid credentials.

So initally, you need to make at least three requests to get your hands on the desired piece of information:

1. Get verficiation token
-------------------------

.. http:get:: /

  Search for the ``__RequestVerificationToken`` and store it's value in a variable. Also make sure to store the cookies in a cookie jar.

  **Example request**:

  .. sourcecode:: http

    GET / HTTP/1.1
    Host: socialclub.rockstargames.com

2. Login using verification token
---------------------------------

.. http:post:: /profile/signin

  Login to Social Club with previously stored verification token. In case you receive ``403`` error, make sure it's no noCAPTCHA interferences.

  **Example request**:

  .. sourcecode:: http

    POST /profile/signin HTTP/1.1
    Host: socialclub.rockstargames.com

  :fparam login: your Social Club account username
  :fparam password: your Social Club account password
  :fparam __RequestVerificationToken: the previously stored verification token

3. Parse actual data
--------------------

Since the cookie jar now has a proper authentication cookie, you can start parsing the information you need.
