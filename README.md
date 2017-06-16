# elm-project

> A Vue.js 饿了么 project
> 
> 打开命令行工具 cd: 到项目目录，输入npm install 回车，即可安装项目中所以的依赖
> 
> 输入 npm run dev  回车。然后在浏览器打开，localhost:8088  即可访问项目
> 
> 在build/webpack.base.config中可以设置alias设置相应的别名，可以在导入时简化路径
> 
> ###vue-router2.0 
> 重定向routes [{path:'/',redirect:{'/', 'goods'}}];不再是1.0中的.go()
> 
> expected "indent", got "eos" 在写stylus时碰到这种问题，肯定是由于编辑器使用了不一样的缩进方式，需要进行设置即可。因为他在你的编辑器中可能是对齐了的，但是实际并没有。
> stylus mixin只可以为样式提供函数的功能
> 
>###Axios
>在vue1.x的时候，vue的官方推荐HTTP请求工具是vue-resource，但是在vue2.0的时候将推荐工具改成了axios。使用方式都差不多，但需要注意的是：接口返回的res并不直接是返回的数据，而是经过axios本身处理过的json对象。真正的数据在res.data里
>
>vue2.0废除了v-el指令，所有的节点指令修改为ref，然后通过ref来获取元素节点，如
><pre><code> 
<div ref="testHook">test</div> ...js code this.$ref.testHook
></code></pre>
>
>###使用emit来发送广播
>
>vue2提供了一套广播机制，即一边发送广播，一边接收广播来执行相应操作。

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```
一些参考文档：

[教学源码](https://github.com/ustbhuangyi/vue-sell)

[better-scroll](https://github.com/ustbhuangyi/better-scroll)

其他人的源码：[1](https://github.com/PacktPublishing/Learning-Vuejs-2/tree/master/chapter4/shopping-list)
[2](https://github.com/RegToss/Vue-SPA)

[flex布局](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)

[vue饿了么踩坑指南](http://www.jianshu.com/p/256abebd4b12)

[http://blog.csdn.net/sinat_17775997/article/details/55189091](http://blog.csdn.net/sinat_17775997/article/details/55189091)

[http://www.cnblogs.com/waitforyou/p/6760807.html](http://www.cnblogs.com/waitforyou/p/6760807.html)

感谢前人的脚步



For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
