# heroku_facebook_bot

This was an exercise in creating a basic facebook chat bot.  It has now been taken offline.


## Building a facebook bot

<img src = "https://en.facebookbrand.com/wp-content/uploads/2016/05/flogo_rgb_hex-brc-site-250.png" align="right" height="100" width="100">

- [Here's a tutorial I liked](https://www.twilio.com/blog/2017/12/facebook-messenger-bot-python.html)
- [Here's the awesome second part](https://www.twilio.com/blog/2018/02/facebook-messenger-bot-heroku-python-flask.html)
- What this bot does: Responds to facebook messenger chats with pre-specified responses it randomly selects

## How this facebook bot works (ngrok)

<img src="https://images.ctfassets.net/3ouphkrynjol/3vuokfMz4AEKwY6EusgKOe/51fc78244e3eb5b9c6ae84141028a90a/ngrok.png" align = "right" height="150" width="150">

- A bit more involved than the twitter bot
- One major difference: you have to host your facebook bot on a webserver so there can be a continuous back and forth of information
- How to get the bot going:
    + Python code is built using [Flask](http://flask.pocoo.org) - a web framework for Python code
    + Create an app on the [facebook developer site](https://developers.facebook.com/apps/) and set up client/access keys/secrets in code and on facebook
    + Use [ngrok](https://ngrok.com) to create a temporary URL for you to host your app from your machine
    + Set up a [webhook](https://sendgrid.com/blog/whats-webhook/) on facebook using this URL for secure back and forth communication between facebook messenger and your webserver
- One thing that confused me: only people you give admin priviledges to your bot on facebook can chat with it unless you submit your bot to facebook for an official review

## How this facebook bot works (heroku)

<img src = "http://logos-download.com/wp-content/uploads/2016/09/Heroku_logo.png" height="150" width = "150" align="right">

- hosting bots via ngrok is bad
    1. need to constantly run both ngrok and your code on your machine to keep your bot to be alive
    2. if you want to update your bot you need to 
        + stop running your python code
        + stop ngrok
        + update python code
        + start running your python code
        + start ngrok
        + update facebook webhook with new ngrok URL
- Solution: heroku
    - Online service that will create a url for you to host stuff
    - set up is relatively easy
    - Main advantage: you can just push updates to your python code to GitHub and they will automatically be deployed to your bot
  
## Main Takeaways

- Its pretty easy to get a basic bot up and running
- Don't need to be super strong in Python, mainly copy and paste
- These bots are very basic but tons of room for creativity
