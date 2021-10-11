Welcome! This is the first backend server for the Rules/Apps solution. This server will be responsible for fetching our "Rules" automatically from the Management API and serving it to our frontend app. You will need to run both servers in order to render all the management data to the frontend client. Here is the link to the other server so you can download it and get started: https://github.com/mei-manzo/Backend-Server-Two.


Instructions:

You'll need to configure the server with your client credentials so that the app can generate your client information- go into index.js and update the following with your information:

var auth0 = new ManagementClient({

    domain: 'YOUR_DOMAIN',
    
    clientId: 'YOUR_CLIENT_ID',
    
    clientSecret: 'YOUR_CLIENT_SECRET',
    
    scope: 'read:users update:users'
});


---

var auth0 = new AuthenticationClient({

    domain: 'YOUR_DOMAIN',
    
    clientId: 'YOUR_CLIENT_ID', //noninteractive client id
    
    clientSecret: 'CLIENT_SECRET'
});

---

var options = { method: 'POST',

    url: 'YOUR_DOMAIN',
    
    headers: { 'content-type': 'application/json' },   
    
    body: '{"client_id":"YOUR_CLIENT_ID","client_secret":"YOUR_CLIENT_SECRET", 
    
    "audience":"YOUR_API_DOMAIN","grant_type":"client_credentials"}' };


Also make sure to update your .env file with the following fields:


DEV_PORT=7001

PROD_PORT=7000

AUTH0_ISSUER_BASE_URL="YOUR_DOMAIN"

AUTH0_CLIENT_ID="YOUR_AUTH0_CLIENT_ID"

BASE_URL=http://localhost:7000

SESSION_SECRET= "YOUR_SESSION_SECRET"
