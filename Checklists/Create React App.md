# Creating React Appplication

- [ ] Initialize New Repository (see GUIDE TBD)
  - run: ``` npm init ```
  - run: ``` npm install express ```
  - run: ``` npm install nodemon --save-dev ```
  - Create Client / Server / Database folders

## Initialize Server

- [ ] Create index.js file in Server folder

  ```javascript
    const express = require('express');
    const path = require('path');

    let app = express();

    const port = 3777;

    app.use(express.json());
    app.use(express.urlencoded({extended: true}));

    app.get('/test', (req, res) => {
      console.log('Endpoint Test Success!');
      res.sendStatus(200);
    })

    app.listen(port, function() {
      console.log(`Listening on Port: ${port}`);
    });
  ```
  
  ## Initialize Client

- [ ] Create index.js file in Client folder

  ```javascript
  
  ```
