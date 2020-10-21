Visualis Web Application

本地调试步骤

1. 修改webapp/server/middlewares/addDevMiddlewares.js

```
 app.use(['/vtproxy'], proxy({
    target: 'http://10.30.66.29:8088', changeOrigin: true, pathRewrite: {
      '^/vtproxy': ''
    }, 
    logLevel: 'debug',
  }))
  app.use(['/image'], proxy({ target: 'http://10.30.66.29:8088', changeOrigin: true }))
```

2. 因为这个项目没有登录，所以需要修改本地cookie，使用代理环境的实际登陆用户的cookie
bdp-user-ticket-id 设置到本地环境实现登陆
