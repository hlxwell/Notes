# Native Mongodb
======
var db = new Db(...)
db.open(function(){
  db.collection("table", function(err, table){
    table.find({}, function(data){
    })
  })
})
======
## All conditional operators:
{'fieldname':{$gte:100}}
$lt, $lte, $gt, $gte and $ne
$in, $nin, $all, $exists, $mod, $size
## Also support regexp
{author:/^Michael/}

# mongoskin
var db = require('mongoskin').db('url')
db.collection('user').find().toArray(function(err, post){
  // do something
})

db.bind('posts', {
  findTop10: function(fn){
    this.find({conditions}, {limit, sort}).toArray(fn);
  },
  removeTagWith: function(tag, fn){
    this.remove({}, fn);
  }
})

# Mongoose
var mongoose = require('mongoose/').Mongoose,
    db = mongoose.connect('mongodb://localhost/event-trigger');

    mongoose.load('./models/');
    User = mongoose.get('User', db);
var user = new User({name:'xx'}};
user.age = 12;
user.save();

User.find({}).each(function(user){
   // user.xxx
}, hydrate);


Collection = mongoose.noSchema('test', db);
Collection.find({}).each(function(doc){
});

More at: 
* http://blog.learnboost.com/blog/mongoose/
* http://mongoosejs.com/