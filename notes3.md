config.js or .config.js or .env.js

Module. Exports = {
	secretKey = ‘3fjalfjae80jlafj’
}

Api keys shouldn’t be pushed to GitHub. 



//command line

Npm init —> package.json

Npm install —save express body-parser

//index.js

Var express = require(‘express’);
Var bodyParser = require(‘body-parser’);

Var app = express();
Var port = 9090; 

App.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: true });

//endpoints

App.get(‘/‘, function(req, res, next) {
	res.status(200).send(‘good to go’);
});

app.listen(port, function() {
	console.log(‘Listening on port: ‘, port);
});

//data structures

Var movies = [{
	title: ‘’, 
	movie_length: 120
}, {}, {}]



// external dependencies
var express = require('express');
var bodyParser = require('body-parser');
var movies = require('./movies');

// app specific variables
var app = express();
var port = 9090;

// MIDDLEWARE - app.use()
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: true }));

// PASSING IN DATA
// pass in data with a get

// Path Params --> req.params

// URL Queries --> req.query

app.get('/', function(req, res) {
  console.log(req)
});

app.listen(port, function() {
  console.log('Listening on port', port);
});


//templating strings


Can’t post more than one object at a time. Have to post an array of objects



//Restful APIs -crud
-follow this standard

//parsing data
-req.body
-req.params —> path params
	-part of the URL
	-/movies/:title
	-req.params.tittle
	-order will matter here
	-common use cases: user accounts e.g. twitter/facebook
	-if theres a space and youre typing it from URL or your front end is being weird, use %20 as a space
	-localhost:3000/movies//Jack%20Libre


.req.query —> URL Queries
-any key=value followed after the ? In the URL
-twitter.com?name=Barbara+Laui

//multiple files - require(‘’);
-categorizing your code into multiple files.
-module.exports
-export out one thing (array, object)
-require that in other files by assigning that to a variable
	var moviesController = require(‘../controllers/movies_controller’);

//request Lifecycle
-the order in which Express calls things 
Express looks at things in the order they are written

//middleware
-functions/actions that will run on every request that is written *after* it. OR if its changed in the endpoint

app.use(bodyParser.json());

//all these routes will use bodyParser as middleware

app.get(‘/‘, function(req, res) {

})

app.use(isAdmin);

//only these routes will use isAdmin middleware
app.post(‘/movies’, function(req, res) {
})

app.post(‘./books’, function(req, res) {
})