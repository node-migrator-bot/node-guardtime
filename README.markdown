# API to access GuardTime services.


Includes GuardTime C API in subdirectory libgt-x.y

How to build:
    npm link
or 
    node-waf configure build test install


Hello world:
    var gt = require('guardtime');
    
    gt.sign('Hello world!', function(err, ts) {
      if(err) {
        return console.error(err);
      } else {
        gt.verify('Hello world!', ts, function(err, res){
          console.log('Ver result: ' + err, res);});
      }
    });

For API documentation please see file [node-guardtime-api.markdown]

For more information about GuardTime Keyless Signature service please go to
[http://www.guardtime.com/].

As You are already here - this is the essence:
GuardTime service adds hash of your doc to giant hash tree with globally unique
root value; and regularily publishes these root values in FT.

Needs Node.JS >= 0.3.0; Windows is not supported.

---
Published under Apache license v. 2.0.
Copyright GuardTime AS 2010-2011
