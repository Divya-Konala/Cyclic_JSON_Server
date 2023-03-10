# To Create JSON Server

## STEP-1: npm init -y
## STEP-2: npm install json-server cors
## STEP-3: npm install -D nodemon
## STEP-4: Create index.js and copy paste the code given below:
<div>
const jsonServer = require('json-server') <br/>
const cors = require('cors') <br/>
const path = require('path') <br/>

const server = jsonServer.create() <br/>
const router = jsonServer.router(path.join(__dirname, 'db.json')) <br/>
const middlewares = jsonServer.defaults() <br/>

server.use(cors()) <br/>
server.use(jsonServer.bodyParser) <br/>
server.use(middlewares) <br/>
server.use(router) <br/>

const PORT = 8000 <br/>

server.listen(PORT, () => { <br/>
  console.log(`JSON Server is running on http://localhost:${PORT}`) <br/>
}) <br/>
</div>

## STEP-5: Create db.json file and enter the data in json format given below:
<div>
{ </br>
    "superHeros": [ </br>
        { </br>
            "id": 1, </br>
            "rating": 10, </br>
            "user_name": "Tony Stark", </br>
            "text": "You are the ironman of this world" </br>
        }, </br>
        { </br>
            "id": 2, </br>
            "rating": 9, </br>
            "user_name": "Bruce Wayne", </br>
            "text": "You are the batman of this world" </br>
        }, </br>
        { </br>
            "id": 3, </br>
            "rating": 8, </br>
            "user_name": "Peter Parker", </br>
            "text": "You are the spiderman of this world" </br>
        } </br>
    ], </br>
    "books": [ </br>
        { </br>
            "bookimageurl": "https://m.media-amazon.com/images/I/710ESoXqVPL.jpg", </br>
            "bookname": "Harrypotter", </br>
            "authorname": "JK.Rowling", </br>
            "genre": "fiction", </br>
            "edition": "2020", </br>
            "publisher": "Amazon", </br>
            "cost": "1500", </br>
            "id": 1 </br>
          },
          {
            "bookimageurl": "https://m.media-amazon.com/images/I/710ESoXqVPL.jpg", </br>
            "bookname": "Harrypotter", </br>
            "authorname": "JK.Rowling", </br>
            "genre": "fiction", </br>
            "edition": "2021", </br>
            "publisher": "Flipkart", </br>
            "cost": "1600", </br>
            "id": 2 </br>
          } </br>
    ] </br>
} </br>
</div>

## STEP-6: In package.json update the following under scripts
"start": "node index.js",</br>
"dev": "nodemon index.js"</br>

<div>
<u>NOTE</u>: When you run "npm run start" in the terminal,it normally runs like node js. Even after updating the data, we have to run the server again. So, inorder to make the server restart itslef after updating the changes, we use nodemon package dependency.(If your system doesn't support nodemon, then try using alternative for this which is supervisor package). To run nodemon, give the command "npm run dev". After running this the console will show this message "JSON Server is running on http://localhost:8000"
</div>

## STEP-7: Deploying globally
To deploy the json server globally, we can use the applications like cyclic.sh, render, railway, etc.
Push the entire code to github and connect this repository with cyclic