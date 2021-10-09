# Creating React Appplication

- [ ] Initialize New Repository (see GUIDE TBD)
  - run: ``` npm init ```
  - Create Client / Server / Database folders

## Initialize Server

- [ ] Create index.js file in Server folder

  ```javascript
    const express = require('express');
    const path = require('path');

    let app = express();

    const port = 3777;

    app.use(express.static(path.join(__dirname, '..', '/client/dist')));
    app.use(express.json());
    app.use(express.urlencoded({extended: true}));

    app.listen(port, function() {
      console.log(`Listening on Port: ${port}`);
    });
  ```
