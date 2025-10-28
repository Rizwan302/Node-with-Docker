🚀 My First Docker + MongoDB + Express Project
📖 Project Overview

Yeh mera pehla project hai jisme maine Docker containers, MongoDB, aur Express.js use kiya hai.
Is project ka main purpose ek simple web form banana tha jahan user apna email, username, aur password enter karke MongoDB database me save kar sakta hai.

----------------------------------------------------------------------------------------------------------------------------------------------------------------

🧰 Technologies Used

Docker – for running MongoDB and Mongo Express containers

MongoDB – database to store user data

Mongo Express – web-based MongoDB admin tool

Express.js – backend framework

HTML & CSS – frontend design

----------------------------------------------------------------------------------------------------------------------------------------------------------------

⚙️ Setup Instructions
🐳 Step 1: Create Docker Network

Sabse pehle ek Docker network create karein jisme MongoDB aur Mongo Express communicate kar sakein:

docker network create mongo-db

🍃 Step 2: Run MongoDB Container

MongoDB ko Docker container me run karne ke liye:

docker run -d \
  --name mongo \
  --network mongo-db \
  -p 27017:27017 \
  -e MONGO_INITDB_ROOT_USERNAME=admin \
  -e MONGO_INITDB_ROOT_PASSWORD=qwerty \
  mongo

🧭 Step 3: Run Mongo Express Container

Mongo Express ko run karne ke liye:

docker run -d \
  --name mongo-express \
  --network mongo-db \
  -p 8081:8081 \
  -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
  -e ME_CONFIG_MONGODB_ADMINPASSWORD=qwerty \
  -e ME_CONFIG_MONGODB_URL="mongodb://admin:qwerty@mongo:27017/" \
  mongo-express


Ab aap apne browser me jaake ye open kar sakte hain:
👉 Mongo Express: http://localhost:8081

👉 MongoDB (local): mongodb://admin:qwerty@localhost:20217


27017

💻 Step 4: Run the Express Server

Project folder me index.js (ya server.js) file run karein:

node index.js


Server run hone ke baad terminal me ye message dikhega:

server running on port 5050

🌐 Step 5: Access the Web Page

Browser me open karein:
👉 http://localhost:5050

Yahan aap ek signup form dekhenge jisme:

Email

Username

Password
enter kar sakte hain aur Create Account button dabakar MongoDB me data save hoga.


📁 Project Structure
my-nodedocker-app/
│
├── public/
│   ├── index.html
│   └── style.css
│
├── index.js          # Express backend
├── package.json
└── README.md


