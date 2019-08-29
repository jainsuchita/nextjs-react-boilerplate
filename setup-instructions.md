# Create a Node.js project
$ mkdir <APP_NAME>
$ cd <APP_NAME>
$ npm init

# Create a .gitignore file with the following content:
.env
node_modules
dist
`This makes sure that your credentials are never saved to GitHub or any other Git provider that you use.`

# Install Typescript and tslint
$ npm install -D typescript
$ npm install -D tslint

# Install Express framework for typescript
$ npm install express -S
$ npm install @types/express -D

# Configuring TypeScript
$ tsc --init
or Create a tsconfig.json with following content:
-------------------------------------------------------
{
    "compilerOptions": {
        "module": "commonjs",
        "esModuleInterop": true,
        "target": "es6",
        "moduleResolution": "node",
        "sourceMap": true,
        "outDir": "dist",
        "baseUrl": ".",
        "experimentalDecorators": true,
        "emitDecoratorMetadata": true,
        "suppressImplicitAnyIndexErrors": true,
    },
    "lib": [
        "es2015"
    ],
    "include": [
        "src/**/*"
    ],
    "exclude": [
        "node_modules",
        "**/*.spec.ts"
    ]
}

# Let’s now configure TypeScript linting for the project.
$ ./node_modules/.bin/tslint --init

add following content to newly created tslint.json file
-------------------------------------------------------
{
    "defaultSeverity": "error",
    "extends": [
        "tslint:recommended"
    ],
    "jsRules": {},
    "rules": {
        "no-console": false
    },
    "rulesDirectory": []
}


# Setting Up The Folder Structure
$ mkdir src
$ cd src
$ touch app.ts

# Creating and Running a Basic Express Server

Open up the app.ts file and paste in the following code
-------------------------------------------------------

import express from 'express';

const app = express();
const port = 3000;
app.get('/', (req, res) => {
  res.send('The sedulous hyena ate the antelope!');
});
app.listen(port, err => {
  if (err) {
    return console.error(err);
  }
  return console.log(`server is listening on ${port}`);
});

# Running TypeScript without transpiling

You can run typescript directly on the node with the ts-node package.
This package is recommended for development only.

$ npm install ts-node-dev -s

Updating the Package.json file
-------------------
"main": "dist/app.js",

"start": "ts-node-dev --respawn --transpileOnly ./app/app.ts",
"build": "tsc && node ./dist/app.js"

we updated the main path and added the start command to the 'npm scripts.' 

# Let’s run the app using the following command:
$ npm start


