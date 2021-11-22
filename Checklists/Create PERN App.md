# Create PERN Application

- [ ] Initialize new repository (GUIDE TBD)
- [ ] Clone GitHub repository to local machine.
- [ ] Inside of cloned repository run the following commands
  - ``` npm init ```
  - ``` npm install pg ```
  - ``` npm install express ```
  - ``` npm install react ```
  - ``` npm install react-dom ```
  - ``` npm install axios ```
  - ``` npm install nodemon --save-dev ```
  - ``` npm install --save-dev webpack webpack-cli```
  - ``` npm install --save-dev @babel/core @babel/cli @babel/preset-env @babel/preset-react babel-loader```

  -  Create schema.sql file
  -  Create webpack.config.js
        ```javascript
          var path = require('path');
          var SRC_DIR = path.join(__dirname, '/client/src');
          var DIST_DIR = path.join(__dirname, '/client/dist');

          module.exports = {
            entry: `${SRC_DIR}/index.js`,
            output: {
              filename: 'bundle.js',
              path: DIST_DIR
            },
            module: {
              rules: [
                {
                  test: /\.(js|jsx)?/,
                  exclude: /node_modules/,
                  use: {
                    loader: "babel-loader",
                    options: {
                      presets: [
                        "@babel/preset-env",
                        "@babel/preset-react"
                      ]
                    }
                  }
                }
              ]
            }
          };
        ```
    
  - Create Client / Server / Database folders
 
  - Create Scripts in package.json:
    -  ``` 
         "start": "nodemon Server/index.js",
         "react-dev": "webpack -d --watch",
         "build-db": "psql postgres < schema.sql"
       ```

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

    app.get('/test', (req, res) => {
      console.log('Endpoint Test Success!');
      res.sendStatus(200);
    })

    app.listen(port, function() {
      console.log(`Listening on Port: ${port}`);
    });
  ```
  
## Initialize Database

- [ ] Create index.js file
  ```javascript
    const { Pool, Client } = require('pg');

    const credentials = {
      host: 'localhost',
      port: 5432,
      user: 'USERNAME_HERE',
      password: null, // 'PASSWORD_HERE',
      database: 'DB_NAME_HERE',
      max: 20,
    };

    const pool = new Pool(credentials);

    pool.connect()
    .then(() => console.log('connected to database'))
    .catch((err) => console.log(err));

    module.exports = {
      query(text, params, callback) {
        const results = await pool.query(text, params, callback);
        return results;
      }
    };
  ```
- [ ] Initialize database by running:
  - ``` npm run build-db ```

## Initialize Client

- [ ] Create dist folder
  - Create style.css file
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
- [ ] Create src folder
  - Create index.js file
  ```javascript
    import React from 'react';
    import ReactDOM from 'react-dom';

    import App from './components/App.jsx';

    ReactDOM.render(<App />, document.getElementById('app'));         
  ```
- [ ] Create components folder
  - create App.jsx
  ```javascript
    import React from 'react';
    import axios from 'axios';
    
    class App extends React.Component {
      constructor(props) {
        super(props);
        
        this.state = {
          test: "STATE TEST SUCCESS"
        }
      }
      
      render() {
        return(
          <div> TEST </div>
        )
      }
    }
    
    export default App;
  ````

