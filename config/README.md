# /config/

> 配置文件

## prod.env.js

> 生产环境

``` bash
# 生产环境变量
module.exports = {
  NODE_ENV: '"production"'
}
```

## dev.env.js

> 开发环境

``` bash
var merge = require('webpack-merge')
var prodEnv = require('./prod.env')

# 开发环境变量，拓展生产环境变量
module.exports = merge(prodEnv, {
  NODE_ENV: '"development"'
})
```

## test.env.js

> 测试环境

``` bash
var merge = require('webpack-merge')
var devEnv = require('./dev.env')

# 测试环境变量，拓展开发环境变量
module.exports = merge(devEnv, {
  NODE_ENV: '"testing"'
})
```

## index.js

> 依环境而定的、预定义的webpack配置

``` javascript
var path = require('path')

module.exports = {
  build: {
    env: require('./prod.env'), // 引入生产环境变量
    index: path.resolve(__dirname, '../dist/index.html'),
    assetsRoot: path.resolve(__dirname, '../dist'),
    assetsSubDirectory: 'static',
    assetsPublicPath: '/',
    productionSourceMap: true,
    productionGzip: false,
    productionGzipExtensions: ['js', 'css']
  },
  dev: {
    env: require('./dev.env'), // 引入开发环境变量
    port: 8080,
    assetsSubDirectory: 'static',
    assetsPublicPath: '/',
    proxyTable: {},
    // 由于css-loader在开启sourceMap时会引发相对路径的bug而关闭
    // 其实可通过设置webpack配置项output.publicPath为绝对路径的方式暂时解决
    cssSourceMap: false
  }
}

```
