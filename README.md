This is an extraction of the Javelin front end library originally developed at Facebook, and now maintained by phacility.
Javelin is an awesome library that is light weight and gives some much needed structure to large JS codebases. For more information on Javelin, check out https://github.com/phacility/phabricator/tree/master/webroot/rsrc/externals/javelin
This is an adaptation based on the Aphlict server used alongside Phabricator (https://www.phacility.com/) with the intention of making it easier to install and use Javelin to structure server side NodeJS code.

Install:
`npm install javelin-js`

Use:
`var JX = require('javelin-js').JX;`

Sample Javelin Module Definition:
```javascript
var JX = require('javelin-js').JX;

JX.install('ModuleName', {
  extends: 'Name of module to inherit from',

  construct: function(param1, param2, ...) {
    // function to initialize an object created with new, ie.
    // var myObj = new JX.MyModule();
  },

  initialize: function() {
    // function called once when the module is first installed
  },

  statics: {
    // static properties or functions associated with the JX module
    // for example, data formatting functions associated with a module
  },

  properties: {
    // these are generally public object members. On install, Javelin generates
    // getters and setters for these properties. For example, if an object had a
    // public id, it could be a property
  },

  members: {
    // properties or functions that are associated with instances of a JX module
    // for example, if you had a module JX.Friend, you may have member properties
    // of name, callFriend(), etc.
  }

})
```
