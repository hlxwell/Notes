# Expressjs:

## var express = require('express')
## var app = express.createServer({options})
createServer can set options. {key: ssl cert}

## Router
app.get('/user/:id', function(req, res){
  req.params.id
  res.send(xxx)
})

/user/:id
/user/:id?
/files/*
/files/*.*
/files/:id/:operations?
/u/:id.:format? => /u/12, /u/12.json
/u/:id(\d+)

## http methods
app.get
app.post
app.del
app.put

## configure for each evn
app.configure('development', function(){
  app.use() => use middleware
  app.set
  app.enable
  app.disable
  app.enabled() => boolean
})

## Middleware
In configure function:
app.use(express.bodyParser()); // will parse json res, req.
also can pass through createServer.
express.createServer(express.logger(), express.bodyParser())

## Next()
app.get(/x/, function(req, res, next) {
 next() // go next route action.
})
next(new Error('无权限'));

## Kind of before filter.
app.all("route", function(){})

## route middleware support multiple callback methods.
app.get('/user/:id', loadUser, function(req, res){})
also more flexible:
var aMiddleware = [middleware1, middleware2]
app.get('/user/:id', aMiddleware, function(req, res){})

## javascript closure is the same to lambda usage in AR model.

## app.use(express.bodyParser()); will parse all json or form data, then you can get them in "req.body"
req.body.user.username

## redirect
res.redirect('back');

## Error processing
function NotFound(msg){
  this.name = 'NotFound in csser.com';
  Error.call(this, msg);
  Error.captureStackTrace(this, arguments.callee);
}

// should be a Error model when throwing out.
NotFound.prototype.__proto__ = Error.prototype; // inherit

app.get('/404', function(req, res){
  throw new NotFound;
});

app.get('/500', function(req, res){
  throw new Error('keyboard cat!');
});

## Global error processing
app.error(function(err, req, res, next){
  if (err instanceof NotFound) {
    res.render('404.jade');
  } else {
    next(err);
  }
});

app.use(express.errorHandler({ 
  dumpExceptions: true, // print error info to stderr
  showStack: true // print error stack
}));

## template rendering engine
1. require('ejs') or require('jade')
2. app.set('view engine', 'jade') // set view engine
3. res.render("index.jade", {title:'xxx', body:'yyy'})
4. res.render("page", {layout: __dirname + '/../layout.jade'})

## render partial
partial("comment", {collection:comments})

## session support
app.use(express.cookieParser());
app.use(express.session({ secret: "keyboard cat" }));

* redis cookie store
var RedisStore = require('connect-redis');
app.use(express.cookieParser());
app.use(express.session({ secret: "CSSer加密字符串", store: new RedisStore }));

* flash
req.flash('info', 'You have %s items in your cart', req.session.items.length);

## Route parameter pre-process
app.param("userId", function(req, res, next, id){
  // process user id
  req.user = User.find(id)
})
// also accept multiple parameters.
app.param(['from', 'to'], function(n){ return parseInt(n, 10); });
app.get("/user/:userId", function(req,res,next){
  req.user
})

## request object
http://expressjs.com/guide.html#req.header()

## Connect provided middleware
docs: http://www.senchalabs.org/connect/
csrf
basicAuth
bodyParser
cookieParser
directory
errorHandler
favicon
limit
logger
methodOverride
query
responsetime
session
static
staticCache
vhost
