# ys-middleware-router

[YS](https://github.com/yskit/ys-mutify) 架构之通用中间件式路由机制

```bash
npm install --save ys-middleware-router
```

# Usage

**router.js**

```javascript
const Router = require('ys-middleware-router');
const route = module.exports = new Router();
route.get('/:id(\\d+)', async ctx => {
  ctx.send({
    a: 1,
    b: 2,
    c: ctx.params.id
  })
})
```

**index.js**

```javascript
const router = require('./router');
module.exports = channel => {
  channel.use(router.routes());
}
```

# License

It is [MIT licensed](https://opensource.org/licenses/MIT).