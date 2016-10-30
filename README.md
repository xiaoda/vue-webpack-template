# vue-webpack-template

> 使用vue-cli初始化的webpack项目

``` bash
# install vue-cli globally
npm install --global vue-cli

# initialize project with webpack
vue init webpack my-project
```

## 根目录文件

### .babelrc

> babel配置文件

``` bash
# babel编译规则包含ES6和ES7第2阶段（实际可用"latest"表示ES6以上的所有特性）
{
  "presets": ["es2015", "stage-2"],
  "plugins": ["transform-runtime"],
  "comments": false
}
```

### .editorconfig

> 统一代码格式的解决方案

``` bash
root = true # 目录

[*]
charset = utf-8 # 编码
indent_style = space # 代码缩进空格代替tab
indent_size = 2 # 缩进长度
end_of_line = lf # 换行符使用lf
insert_final_newline = true # 文件末尾始终留一行空
trim_trailing_whitespace = true # 空行不能有空格
```

### .eslintignore

> eslint忽略特定的文件和目录

``` bash
build/*.js # 编译脚本
config/*.js # 配置文件
```

### .gitignore

> git忽略特定的文件和目录

``` bash
.DS_Store # MacOS系统文件
node_modules/ # 项目依赖第三方文件
dist/ # 编译文件
npm-debug.log # npm错误日志
test/unit/coverage
test/e2e/reports
selenium-debug.log
```

### index.html

> 入口文件

### package.json

> 项目说明

### README.md

> 就是我呀！

## 一级目录

- build
- config
- node_modules
- src
- static
- test

## 默认脚本

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```
