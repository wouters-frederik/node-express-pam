PAM-auth
=======
A simple BASIC authenticator for Node.js implemented as a connect (express) middleware that uses PAM for authentication. PAM-auth uses the Basic authentication method provided by http.  If you aren't using https this is insecure because username/passwords are transported in cleartext.  

This is useful for when you don't want to have to make a user system, but you want to limit access.  With this module you can simply use your system user database to manage users.  

Quick Start (Ubuntu)
-----------
1) To interface with PAM we need a dev package:
   sudo apt-get install libpam0g-dev

2) Install pam-auth with npm:
   npm install pam-auth
   (or add pam-auth to your package.json and 'npm install')

3) 'use it!
```javascript
var pam_auth = require('pam-auth');
app.use(pam_auth("MySite"));
```

Thats it!

More Detail
-----
The interface:
   function pam_auth(realm, module)

Both arguments are optional.  Realm defaults to "Login Required", and module defaults to 'passwd' for linux and 'chkpasswd' for macosx.  


