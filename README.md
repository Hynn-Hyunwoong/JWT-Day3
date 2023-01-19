# Front Part

```sh
npm init -y
npm install express nunjucks axios cookie-parser
```

## Setup Server.js
```js
const express = require('express');
const app = express();
const nunjucks = require('nunjucks');
const cookieParser = require('cookie-parser');
const axios = require('axios');

app.set("view engine", "html");
nunjucks.configure("views", {
    express : app,
})

app.use(cookieParser());
app.use(express.json());
app.use(express.static("public"));

app.get('/', (req,res) => {
    res.render('index.html')
});

app.listen(3005, ()=>{
    console.log('listening on port on 3005')
});
```

### Default setting index.html (Included axios script)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>
    <title>Test Front Code</title>
</head>
<body>
    <h1>Logo</h1>
    <ul>
        <li><a href="#">About</a></li>
        <li><a href="#">Board</a></li>
        <li><a href="#">Sign in</a></li>
        <li><a href="#">Sign up</a></li>
    </ul>
    <div id="main">Main Area</div>
</body>
</html>
```

####