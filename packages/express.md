Install Express Globally
========================

```
# npm install -g express
$ express --version; # this doesn't seem to work
$ npm list -g | grep express; # this will verify the version of express
```

If that doesn't work, install the express generator.
```
# npm install -g express-generator@4
$ express --version
```

Express Application Generator
=============================
Use the application generator tool, `express`, to quickly create an application skeleton.

- Install it with the following command.
  ```
  $ npm install express-generator -g
  ```
  
To Create an Express App
========================

- The following creates an Express app named _**myapp**_ in the current working directory.
  ```
  $ express myapp
  ```

- Then install dependencies and run the app.
  ```
  $ cd myapp
  $ npm install
  $ DEBUG=myapp ./bin/www
