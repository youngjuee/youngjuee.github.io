---
title: express + mongodb 연결
category: MongoDB
---

express서버와 mongodb를 연결해서 monster collection에 있는 데이터값을 불러오려고 했다.
<br>
db연결 하는 방법 : 

```
const express = require('express');
const app = express();
const bodyParser = require('body-parser');
const port =process.env.PORT || 3001;
const admin = require('./models/admin')
const router = require('./router/main')(app, admin)
const mongoose = require('mongoose');


mongoose.connect('mongodb://master:gjeorjs18!@111.118.29.66:23284/admin',{useNewUrlParser:true, useUnifiedTopology: true})
//mongoose.connect('master:gjeorjs18!@111.118.29.66:23284/admin',{useNewUrlParser:true, useUnifiedTopology: true})
  .then(() => console.log('Successfully connected to mongodb'))
  .catch(e => console.error(e));
app.use(bodyParser.json());



app.listen(port, () => console.log(`Example app listening on port ${port}!`))
```