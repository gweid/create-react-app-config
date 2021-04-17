# 阅读 create-react-app 的相关配置



## 准备

首先，通过 create-react-app 快速生成一个 react 项目

```js
create-react-app create-react-app-config
```

接着，进到项目里面，打开 package.json，可以看到：

```js
{
  "scripts": {
    "start": "react-scripts start", // 启动开发环境
    "build": "react-scripts build", // 生产环境到
    "test": "react-scripts test",
    "eject": "react-scripts eject" // 暴露配置
  }
}
```

执行 `npm run eject` 暴露配置

暴露配置之后，再看 package.json，会发现变成了：

```js
{
  "scripts": {
    "start": "node scripts/start.js",
    "build": "node scripts/build.js",
    "test": "node scripts/test.js"
  },
}
```

相应的目录结构变成了：

![](/imgs/img1.png)

多了两个目录：

- config 目录：react 项目的 webpack 相关配置
- scripts目录：存放`npm run start/build/test` 的执行文件 



## 启动及配置文件分析

比较主要的就是 scripts/start.js 和 scripts/build.js 下面的两个文件以及 config/webpack.config.js 文件，分析注释说明写在相关文件里面。



