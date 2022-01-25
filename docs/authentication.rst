Authentication procedure
========================

Note
####
To quote GLADoS from Portal 2, the best solution to a problem is usually the easiest one, and I'll be honest, solving Arkose Labs CAPTCHA is hard. I am contributing to this to help future enthusiasts not suffer the pain I had to to finally start completing automated tasks on Social Club.
If you'd like to read about an "easier" solution to logging in (the first and hardest step), and in a way that maintains session presence and does not require complex authentication subroutines, please scroll to the bottom.

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

Alternative
===========
If you are using Node JS, Puppeteer is a really cool interface which you can create and run scripts that can visit websites, search for selectors, scrape information, and in this case help us bypass CAPTCHA and other robot hating systems by "puppeteering" Chrome as a headless browser. Puppeteer renders websites it visits as if it was a "human" client, which makes it pretty difficult to stop.

Puppeteer is also a popular package that has a bunch of support via Google if you ever get stuck. A lot of code you can find is copy and paste friendly, as it is a very straightforward package to use. I.E. ``page.click('#myButton');`` It's THAT simple.

Once you've gotten started with Puppeteer. Basically you want to visit the Rockstar Social Club website with puppeteer running "headfull", where headless is set to false. You will also need to define a userDataDir, which is going to be where all the legitimate cookies and "human" data is going to be cached and stored. These options are set when instancing the puppeteer browser:

.. sourcecode:: js
  
  const browser = puppeteer.launch({
    headless: false,
    userDataDir: './myUserDataDir',
  });


This is important, because while the Chrome instance appears human, it is a new device and Arkose labs is going to throw a CAPTCHA at it anyways. Basically we are going to want to create a page, head to Social Club, and wait to allow us to complete the next step.

.. sourcecode:: js
  
  const page = await browser.newPage();
  page.setDefaultTimeout(10000);
  page.setCacheEnabled(false);
  //I used my browser's viewport for this. Just trying to make it look as human as possible.
  await page.setViewport({
    width: 1920,
    height: 937,
    deviceScaleFactor: 1,
  });
  
  //Human looking User Agent is required
  await page.setUserAgent('Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/61.0.3163.100 Safari/537.36');
  await page.goto('https://signin.rockstargames.com/connect/authorize/socialclub?lang=en-US&returnUrl=%2F');
  await page.waitFor(360000);
  
When the page loads (and it will open a Chromium browser), just take control of it and log in with your bot account's user credentials. waitFor keeps the page open for a while. Once you pass the CAPTCHA, Social Club will trust your bot at that IP address. This can be problematic for deployments because it is not cost effective to install a remote desktop to help your bot pass a captcha, but you only need to do it once for that IP, so worth? Google charged me for using "premium" bandwidth during the remote desktop streaming session as the data also had to travel over the ocean. Just understand that the set up process, while a little tedious with remote servers, is doable and I prefer it to the alternative.

Once your credentials are trusted, and you've logged in. Exit the browser and run a test to see if the bot can navigate to it's own profile. If it can without needing to log in, you are set! Puppeteer offers other advantages as well, including request interception. This will be useful later when you are trying to get access to stats, whereas waiting for a webpage to render and scraping it is inefficient vs. snagging the data payload that the website recieves from Rockstar Servers.
