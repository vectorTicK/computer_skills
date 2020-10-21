# Ubuntu环境使用node.js

*javascript语言后端框架*

### 安装node.js

1. 打开终端
2. 运行`sudo apt-get install nodejs npm`
3. 检查安装情况`node -v` `npm -v`

### 使用express框架

1. 安装express

   `npm i express@next `

2. node中引用express包

   ```javascript
   const express = require('express')
   const app = express()
   app.listen(3000, () => {
       console.log('App is listening on port 3000')
   })
   ```

3. express路由

   ```javascript
   app.get('/', (req, res) => {
       res.send({page:'home'})
   })
   ```

   **tips**

   使用nodemon监听程序改变，不用每次修改文件后重新手动运行

   

4. 

### MongoDB数据库

1. ubuntu 20.04下安装MongoDB

   - 下载安装程序 `https://www.mongodb.com/try/download/community`
   - 双击安装

2. 启动MongoDB

   ```bash
   sudo systemctl start mongod
   ```

3. node中使用MongoDB
   使用mongoose包

   - 安装 `npm i mongoose`

   - 连接数据库

     ```javascript
     const mongoose = require('mongoose')
     mongoose.connect('mongodb://localhost:27017/express-test', {
         useNewUrlParser: true,
         useUnifiedTopology: true
     })
     ```


   - 建立数据模型、插入查询数据

     ```javascript
     const Product = mongoose.model('Product', new mongoose.Schema({
         title: String
     }))
     // init data
     Product.insertMany([
         {title: '产品1'},
         {title: '产品2'}
      ])
     app.get('/products',async (req, res) => {
         res.send(await Product.find())
     })
     ```

     

