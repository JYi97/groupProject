Create backend and frontend folders

Create .gitignore file

In the backend folder, initialize the server's package.json by running npm init -y

`npm install` the following packages as dependencies:

npm i bcryptjs - password hashing
npm i cookie-parser - parsing cookies from requests
npm i cors - CORS
npm i csurf - CSRF protection
npm i dotenv - load environment variables into Node.js from a `.env` file
npm i express - Express
npm i express-async-handler - handling `async` route handlers
npm i express-validator - validation of request bodies
npm i helmet - security middleware
npm i jsonwebtoken - JWT
npm i morgan - logging information about server requests/responses
npm i per-env - use environment variables for starting app differently
npm i pg@">=8.4.1" - PostgresQL greater or equal to version 8.4.1
npm install sequelize@5 - Sequelize
npm i sequelize-cli@5 - use `sequelize` in the command line

npm i -D dotenv-cli - use `dotenv` in the command line
npm i -D nodemon - hot reload server `backend` files

Create .env in backend
PORT=
DB_USERNAME=
DB_PASSWORD=
DB_DATABASE=
DB_HOST=
JWT_SECRET=
JWT_EXPIRES_IN=

Run openssl rand -base64 10 to generate a random JWT secret

Create config folder in backend with index.js

Set up backend/db folder to contain all files for models, seeders, and migrations by creating a .sequelizerc file in the backend folder

Initialize Sequelize to the db folder by running: npx sequelize init

Replace the contents of the newly created backend/config/database.js

Create a user using the same credentials in the .env file with the ability to create databases:
psql -c "CREATE USER <username> PASSWORD '<password>' CREATEDB"

Create the database using sequelize-cli:
npx dotenv sequelize db:create

Create a file called app.js in the backend folder

Create a folder in backend called bin. Inside of it, add a file called www

In your package.json, add the following scripts:
  "scripts": {
    "sequelize": "sequelize",
    "sequelize-cli": "sequelize-cli",
    "start": "per-env",
    "start:development": "nodemon -r dotenv/config ./bin/www",
    "start:production": "node ./bin/www"
  }

Run npm start in the backend folder
http://localhost:5000/hello/world
