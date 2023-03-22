What the title says... here it is. Can also keep any NodeJS script alive, no matter the host.

NOTE: If your server provider gives a random port, use method 1, replace `const port = 3000;` with `const port = process.env.PORT || 3000;`
```
//Create a new file called keep_alive.js in the same folder as the main file of your bot and paste this code there.


//--------------------- keep_alive.js file START -----------------------------------|


const express = require('express');
const app = express();
const port = 3000;
app.listen(port, () => console.log(`Bot running on http://localhost:${port}`));


//--------------------- keep_alive.js file END -------------------------------------|





//Add this code to the main file of your bot.


//------------------------------- CODE START ---------------------------------------|


const { keep_alive } = require("./keep_alive");


//-------------------------------- CODE END ----------------------------------------| 
```
Way 2
```
New File, html.js with the code ---------------->

const http = require("http");
http.createServer((_, res) => res.end("Bot is Online")).listen(8080)


-------------end code----------->


and add the following line to the main file of your bot ---------------->
require ("./html.js");




