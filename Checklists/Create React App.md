# Creating React Appplication

- [ ] Initialize New Repository (see GUIDE TBD)
  - run: ``` npm init ```
  - run: ``` npm install express ```
  - run: ``` npm install nodemon --save-dev ```
  - run: ``` npm install webpack --save-dev ```
  - Create Scripts in package.json:
    -  ``` "start": "nodemon Server/index.js" ```
    -  ``` "react-dev": "webpack -d --watch" ```
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
  
## Initialize Database

- [ ] Checklist In Progress...

## Initialize Client

- [ ] Create dist folder
  - Create index.html file
    ```html
      <!DOCTYPE html>
      <html>

        <head>
          <title>TITLEHERE</title>
          <link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">
          <link rel="stylesheet" href="styles.css">
        </head>

        <body>
          <h1>Header Here</h1>
          <div id="app"></div>
          <script type="text/javascript" src="bundle.js"></script>
        </body>

      </html>

    ```

- [ ] Create index.js file in Client folder

  ```javascript

  ```
