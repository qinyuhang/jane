## jane
![cover](./cover.jpg)
+ scss、less、async、await、api的promise化处理

## Install
```
sudo npm install -g @linhun/jane
```

## Features
+ .scss -> .wxss 
+ es6 -> es5
+ async、await
+ 支持js sourcemap
+ build -w .scss支持依赖检查

## Quickstart
init project
``` sh
jane new project
```
build project
``` sh
jane build // on production
jane build -w // watch build on develop
```
config file
```javascript
module.exports = {
  dest:'build', // build dir
  tpl:{ // custom page dir
    page:'' // must be directory
  },
  css: {
    ext:'.scss', // css ext
    compiler: 'scss', // define css compiler
    config:{} // css compile by node-sass. option is same as:https://github.com/sass/node-sass
  },
  js: {
    ext:'.js',
    compiler: 'babel',
    // https://babeljs.io/docs/usage/api/
    config: {
      presets:['env'],
      plugins:["transform-async-to-generator"] // babel-plugins 
    }
  },
  ignore:['node_modules','dist','.DB_store','.DS_Store'] // these files could be ignored by compiler
}
```
## More usage
jane --help
```
  Usage: jane [options] [command]
  
  Options:

    -v, --version  显示版本号
    -w, --watch    监视目录改动
    -h, --help     output usage information


  Commands:

    clean          清空build目录
    build          编译项目
    new <project>  新建项目
    page <page>    新建页面
    upgrade        更新

```
## Todo 
+ image minify

## License
MIT


