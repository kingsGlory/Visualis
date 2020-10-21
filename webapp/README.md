Visualis Web Application

本地调试步骤

1. 修改webpack/webpack.dev.babel.js

```
 proxy: {
      '^/vtproxy': {
        target: 'https://saas.ctyun.cn:8086',
        ws: true,
        changeOrigin: true,
        pathRewrite: {
          '^/vtproxy': ''
        }
      },
```

2. 因为这个项目没有登录，所以需要修改本地cookie，使用代理环境的实际登陆用户的cookie
bdp-user-ticket-id 设置到本地环境实现登陆
