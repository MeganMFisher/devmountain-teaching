//REQUIRE MODULES
var express = require('express');
var bodyParser = require('body-parser');

//INITALIZE EXPRESS
var app = express();
//DECLARE PORT
var port = 9091;

//MIDDLEWARE
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: true }));

//ENDPOINTS
app.get('/', function(req, res){
    //request from client
    //respons TO CLIENT from SERVER
    res.status(200).send('Haaaaaiio')
})

//note: this will not work without bodyParser middleware
app.post('/', function(req, res){
    console.log('body', req.body);
})

//LISTEN
app.listen(port, function() {
    console.log('Listening on port ', port)
})



1. Generate package.json --> npm init
2. install and save modules that we want to use --> npm install --save express body-parser express-sessions
3. create our server file: 
    -touch index.js 
4. (in index.js)
    -require modules    
    -use modules
    -listen on a port
    -add server specific logic like *middleware*, *ENDPOINTS*, *session*, *static assests*


<!--### express.static(__dirname + 'foldername')
Serves up our front end/client code on the same domain as our server. 
Everything we serve up here is public
-common names for this folder *public*, *static*, *assets*-->

<!--## CORS
cross origin resource sharing
by default, different domains cannot make requests of each other 
this must be enabled

### sessions
To track and record user state across different request
-so you can identify who made what request
-to imporove user experience on your application
-user authentication
-anything where you want to track user state

## express-session
npm install --save express-session

app.use(session({
    secret: config.SESSION_SECRET,
    resave: false, 
    saveUninitialized: true
}))-->

<!--//if you have HTTPS set up, you should set cookie: { secure : true }
//if you do this with HTTP, the cookie shoud be set to false or  the default but you won't be able to save the user state.

//Session information is available on req.session-->
