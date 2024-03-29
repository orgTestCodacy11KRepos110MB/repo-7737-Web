npm又称为包管理工具。



一般安装nodejs时会自带npm管理工具。



测试npm是否安装成功：

```js
npm -v
```

如果能成功打印版本号则安装成功。



如果需要使用npm下载安装软件，需要在项目下有一个`package.json` 文件。这个文件可以自己创建，也可以使用npm指令创建，用npm指令创建简单一些，不用在意修改其中的内容。

## 创建模块化开发项目

**1、创建package.json文件**

```js
npm init
```

创建的过程中会提示输入项目的名称等等一些问题，如果不在意的话，一路回车即可。

**2、向项目添加工具（这里以jQuery为例）**

```js
npm install jquery --save // npm i jquery --sava
```

> 参数 `--save`或者`-S` 该模块为项目依赖(运行依赖)
>
> 参数 `--save-dev`或`-D` 该模块为开发依赖(例如less就是开发依赖，开发的时候才使用，上线之后就不用了，用它生成的css文件)
>
> 参数 `-g`  全局安装某个模块



**3、卸载某个工具（已jQuery为例）**

```js
npm uninstall jquery -S   // uninstall没有简单写法，后面的参数就是安装时的参数
```



> 有的时候安装失败的时候，仅仅卸载的话，可能还有缓存存在，可能导致下次安装不成功。所以每次在安装失败的时候，都应该卸载之后，再次运行清除缓存的操作。
>
> 清除缓存操作指令如下：
>
> ```js
> npm cache clear -f
> ```



还有一些其他的npm指令：

```js
npm info jquery //查看模块的相关信息
npm run start   //执行package.json 中的script属性的脚本
```

## nrm

有的时候，npm访问的速度特别慢，是因为npm的主机是在国外的。幸运的是，国内有几个良心公司为了方便国内用户方便下载npm中的工具，于是在国内做了几个npm镜像主机，我们在国内访问这些镜像主机的时候，速度就很快了。

### nrm 的安装使用

nrm指令作用：提供了一些最常用的NPM包镜像地址，能够让我们快速的切换安装包时候的服务器地址。

什么是镜像：原来包刚一开始是只存在于国外的NPM服务器，但是由于网络原因，经常访问不到，这时候，我们可以在国内，创建一个和官网完全一样的NPM服务器，只不过，数据都是从人家那里拿过来的，除此之外，使用方式完全一样，这个地址就是镜像地址。

1. 运行`npm i nrm -g`全局安装`nrm`包；
2. 使用`nrm ls`查看当前所有可用的镜像源地址以及当前所使用的镜像源地址；
3. 使用`nrm use npm`或`nrm use taobao`切换不同的镜像源地址；

> 注意： nrm 只是单纯的提供了几个常用的下载包的 URL地址，并能够让我们在这几个地址之间切换，很方便的进行切换，但是我们每次装包的时候，使用的装包工具，都是 npm

![](./images/24.png)


> 注意：切换完源之后，软件的下载还是通过npm，nrm只是用来切换下载源的。


### npm、nrm、nvm是什么关系？

- npm(node.js package management)：node.js 包管理，用于管理node.js包的下载等等
- nrm(node.js resource management)： node.js 下载源管理，用于切换下载源，实现快速下载包
- nvm(node.js version management) ：node.js版本管理，用于管理多个node.js版本共存、切换等

参考链接：https://juejin.cn/post/6844903718123470861




