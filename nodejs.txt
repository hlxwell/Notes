Node.js

# Modules

when define module in "foo.js" file.
===============
var PI = Math.PI; // will be private vars.
exports.area = function(r) {
  return PI * r * r;
}
===============
require 'foo.js'
// will have area(r) function here.
===============

# Core Modules
require('http') is loading system modules, which is located at "node_modules" folder. search path will like:
* /home/ry/projects/node_modules/bar.js
* /home/ry/node_modules/bar.js
* /home/node_modules/bar.js
* /node_modules/bar.js

# Folder as module
when require("folder_name") it will find "package.json" file, which like:
{ "name" : "some-library",
  "main" : "./lib/some-library.js" }
and it will load the "mail" js. or else it will find *index.js* or *index.node*

# Caching
once you require("foo"), then next time each require("foo") will return same object.