---
layout: post
title: "25X-03-node with express"
tags: ["Nodejs", "Expressjs"]
categories: ["Computer Science"]
published: true
date: 2021-05-18 15:03:37 +0800
---



## Objective

Given the request for developing a simple backend server, I spend an afternoon on researching the serious of [Express.js](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs). Here is notes for what I have studied.

Express reminds me Flask, anything is plug in and plug out anytime. Do not worried about there are any fixed methods forced you to use. There are a few prospectives I should be careful about:

1. HTTP verb
2. URL pattern
3. Template view
4. middleware
5. database mechanism

## Hello World

```javascript
// HelloWorld.js
const express = require("express");
const app = express();
const port = 3000;

app.get("/", (req, res) => {
    res.send("Hello World.")
})

app.listen(port, () => {
    conosle.log("Listening @ 3000.")
})
// End
```

<br />

*A common convention for Node and Express is to use error-first callbacks.*

Called in any request methods

```javascript
// allMethod.js
app.all("/secret", (req, res, next) => {
    console.log("hihi");
    next();
})
// End
```

<br />

*Often it is useful to group route handlers for a particular part of a site together and access them using a common route-prefix.*

```javascript
// wiki.js
const express = require("express");
const router = express.Router();

router.get("/", (req, res) => {
    res.send("wiki home page");
})

router.get("/about", (req, res) => {
    res.send("About");
})

module.exports = router;
// End
```

And  the import into `index.js`

```javascript
// index.js

const wiki = require("./wiki.js");
// ...
app.use("/wiki", wiki);
```

On the other hand, we should module up middlewares into other files like dealing with route handlers as usual.

```javascript
// middleware
const express = require("express");
const app = express();

let a_middleware_function = (req, res, next) => {
    // ...
    next();
}

// For all routes and verbs
app.use(a_middleware_function);

// For specific route
app/use("/someroute", a_middle_function);

// For specific HTTP verb and route
app.get("/", a_middleware_function);

app.listen(3000)
```



<br /> 

I change the tutorial to [this site](https://rahmanfadhil.com/express-rest-api/) for explaining more details in connecting Express with Mongooese. Too much extra information in the original site.