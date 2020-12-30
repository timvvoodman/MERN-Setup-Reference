# MERN-Setup-Reference
MERN App reference tool with setup instructions, sample snippets, and sample app

PART I: SETTING UP THE PROJECT
1. File Structure Setup
  - 
2. Seting up the React Application
    - add css libraries

3. Setting Up the react Router
4. Creating Compnents
5. Creating Layout and Navigation


PART II SETTING UP THE BACK-END

1. Initiating The back-end
  - create package.JSON file ```npm init -y```
  - add dependencies: ```npm install``` express body-parser cors mongoose
  - install global package ```npm install -g nodemon```

2. Create the server.js File
  - within the specified folder ```touch server.js```
  - initiate the node.js/express server in the server.js file 
const express = require('express');
const app = express();
const bodyParser = require('body-parser');
const cors = require('cors');
const PORT = 4000;

app.use(cors());
app.use(bodyParser.json());

app.listen(PORT, function() {
console.log("Server is running on Port: " + PORT);
})

  - start the server with nodemon ```nodemon server```

3. Installing MongoDB
  - https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/
  - create data directory for mongoDB ```mkdir -p /data/db```
  - ensure user account running mongodb has read/write permissions for the directory
  - start up mongoDB ```mongod```

4. Create a New MongoDB Database
  - connect to database server ```mongo```
  - create database ```use todos```

5. Connect to MongoDB using mongoose
  - In the server.js file add... 

const express = require('express');
const app = express();
const bodyParser = require('body-parser');
const cors = require('cors');
const mongoose = require('mongoose');
const PORT = 4000;

app.use(cors());
app.use(bodyParser.json());

mongoose.connect('mongodb://127.0.0.1:27017/todos', { useNewUrlParser: true });
const connection = mongoose.connection;

connection.once('open', function() {
    console.log("MongoDB database connection established successfully");
})

app.listen(PORT, function() {
    console.log("Server is running on Port: " + PORT);
});

6. Create Mongoose Schema
  - add a file to db folder ```todo.model.js```
  - Add starting schema code..(lines 1-17)

7. Implement The Server Endpoints  
  - Add get request for all available todos items
  - 



  