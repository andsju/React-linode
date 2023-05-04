# MERN stack: localhost and Linode

server - client

## server 

application listen on port 3001

localhost:3001
localhost:3001/api  "Hello world"

## client

localhost:3000      "Hello world"

Client side uses file `/src/setupProxy.js` to set port to communicate 

```js
const { createProxyMiddleware } = require('http-proxy-middleware');

module.exports = function(app) {
  app.use(
    '/api',
    createProxyMiddleware({
      target: 'http://localhost:3001',
      changeOrigin: true,
    })
  );
};
```



https://www.freecodecamp.org/news/how-to-create-a-react-app-with-a-node-backend-the-complete-guide/
https://stackoverflow.com/questions/70374005/invalid-options-object-dev-server-has-been-initialized-using-an-options-object


# Linode

1 Create new linode

Debian 11 image

Using console

login as root

```sh

curl -fsSL https://deb.nodesource.com/setup_current.x | sudo -E bash -

sudo apt install nodejs

node -v

sudo apt-get install git-all

mkdir website

cd website

git clone https://github.com/andsju/mern.git

cd mern/server

npm install

npm install pm2

pm2 start server

cd mern/client

npm install

npm start

```

visit 
- localhost:3001
- localhost:3001/api  "Hello world"
- localhost:3000  "Hello world"