# preinstall 安装前钩子

我们执行 `npm install xxx` 安装前 `preinstall` 钩子会被执行。我们先看一个最简单的例子

首先我们创建一个 `hello-preinstall.js` 文件，内容如下：

```js

console.log(`


###########################################
############ Hello preinstall #############
###########################################


`);

```

然后我们再 `package.json` 中创建 `preinstall` 脚本：

```json
{
    "name": "hello-preinstall",
    "version": "1.0.0",
    "main": "index.js",
    "license": "MIT",
    "scripts": {
        "preinstall": "node index.js"
    }
}
```

这时候我们随便安装一个 npm 包，就会在安装前，执行我们的 `preinstall` 脚本。我们选择一个体积小的 npm 包：`which-pm-runs`

```bash
yarn add which-pm-runs
```

结果如下：

```bash
yarn add which-pm-runs
yarn add v1.22.19
$ node index.js



###########################################
############ Hello preinstall #############
###########################################



[1/4] 🔍  Resolving packages...
```

[Demo 地址](../../src/scripts/preinstall/hello-preinstall/);