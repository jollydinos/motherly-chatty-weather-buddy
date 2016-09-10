# Chatty Weather
A handy weather app delivering customizable weather forecasts and helpful recommendations using the MEAN stack

## Information Flow
  CLIENT-SIDE  
      &nbsp;&nbsp;- Weather controller loads =>   
      &nbsp;&nbsp;- Loads goGet factory, runs its getWeatherData function =>  
      &nbsp;&nbsp;- Makes a GET request to /api/weather =>  
  SERVER-SIDE  
    (Router picks up on this)  
    WEATHER CONTROLLER  
      &nbsp;&nbsp;- Makes a GET request to https://api.forecast.io =>  
      &nbsp;&nbsp;- Receives back a huge object with tons of forecasting info =>  
    LOGIC CONTROLLER  
      &nbsp;&nbsp;- Parses huge object into useful info =>  
      &nbsp;&nbsp;- req.body and req.query now consist of this parsed info =>  
    TRANSPORTATION CONTROLLER  
      &nbsp;&nbsp;- Gets current subway info =>  
      &nbsp;&nbsp;- Adds to req.query =>  
    PHRASES CONTROLLER  
      &nbsp;&nbsp;- Gets relevant phrases given the weather-related info held in req.body =>  
      &nbsp;&nbsp;- Parses relevant info in req.body, and adds it to phrases obj =>  
      &nbsp;&nbsp;- Responds with json obj of phrases, which gets passed back to client

## Directory Layout

    app.js              --> app config
    package.json        --> for npm
    client/             --> all of the files to be used in on the client
        app.js          --> declare top-level app module
        activities      -->  files for activities components
        assets          --> folder containing styling elements
          css/              --> css files
        food            --> files for food components
        weather         --> files for weather components
        services        --> factories for components
        lib/            --> angular and 3rd party JavaScript libraries
    ext/                --> all of the files to be used for Google
                            Chrome extension
    web/
      activities          --> logic for GET and POST activities from API
      food                --> logic for GET and POST food from API
      phrases             --> logic and models for phrases DB
      weather             --> logic for GET and POST weather from API
      db.js               --> configuring with DB and environment port
      server.js           --> setting up server connection
      router.js           --> event handlers for components from DB and
                                  data from API

## Features added by the Dinos
  ### FEATURE: MTA info
  ### FEATURE: Hourly weather report
  ### FEATURE: Music
  ### FIX: Food & Activity page formatting
  ### FIX: Scrollbar
