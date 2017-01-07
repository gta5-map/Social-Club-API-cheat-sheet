# Authentication procedure

If you take a look at the login/`<form>` element, you see a hidden `<input>` tag called "__RequestVerificationToken". This contains a token which is needed in the actual login request otherwise Rockstar refuses the authentication, even with proper credentials.

So basically, you need to make at least three requests to get your hands on the desired piece of information:

1. Send _GET_ request to "http://socialclub.rockstargames.com/" and search for `__RequestVerificationToken`. Store it's value in a variable and the cookie in a cookie jar.

2. Send a _POST_ request to "https://socialclub.rockstargames.com/profile/signin". Don't forget to use the cookie jar from the first request and store the new authentication cookie in it as well:

    - `login="<SOCIALCLUB_USERNAME>"`  
    - `password="<SOCIALCLUB_PASS>"`   
    - `__RequestVerificationToken="<STORED_RVT>"`

3. Since the cookie jar now has a proper authentication cookie, you can start parsing the information you need.
