# vuehr

> A Vue.js project

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

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).


5.进入到vuehr目录中，在命令行依次输入如下命令：

# 安装依赖
npm install

# 在 localhost:8080 启动项目
npm run dev
由于我在vuehr项目中已经配置了端口转发，将数据转发到SpringBoot上，因此项目启动之后，在浏览器中输入http://localhost:8080就可以访问我们的前端项目了，所有的请求通过端口转发将数据传到SpringBoot中（注意此时不要关闭SpringBoot项目）。

6.最后可以用WebStorm等工具打开vuehr项目，继续开发，开发完成后，当项目要上线时，依然进入到vuehr目录，然后执行如下命令：

npm run build
该命令执行成功之后，vuehr目录下生成一个dist文件夹，将该文件夹中的两个文件static和index.html拷贝到SpringBoot项目中resources/static/目录下，然后就可以像第4步那样直接访问了。


# 报错：

ERROR  Failed to compile with 1 errors                                                                                                           2:49:15 PM

 error  in ./src/App.vue

Module build failed: Error: 

Vue packages version mismatch:

- vue@2.5.13 (/Users/tangdengxian/crc/codeLib/CrcTimeSheet/CrcTimeSheetWeb/node_modules/vue/dist/vue.runtime.common.js)
- vue-template-compiler@2.6.10 (/Users/tangdengxian/crc/codeLib/CrcTimeSheet/CrcTimeSheetWeb/node_modules/vue-template-compiler/package.json)

This may cause things to work incorrectly. Make sure to use the same version for both.
If you are using vue-loader@>=10.0, simply update vue-template-compiler.
If you are using vue-loader@<10.0 or vueify, re-installing vue-loader/vueify should bump vue-template-compiler to the latest.

    at Object.<anonymous> (/Users/tangdengxian/crc/codeLib/CrcTimeSheet/CrcTimeSheetWeb/node_modules/vue-template-compiler/index.js:10:9)
    at Module._compile (internal/modules/cjs/loader.js:689:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:700:10)
    at Module.load (internal/modules/cjs/loader.js:599:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:538:12)
    at Function.Module._load (internal/modules/cjs/loader.js:530:3)
    at Module.require (internal/modules/cjs/loader.js:637:17)
    at require (internal/modules/cjs/helpers.js:20:18)
    at Object.<anonymous> (/Users/tangdengxian/crc/codeLib/CrcTimeSheet/CrcTimeSheetWeb/node_modules/vue-loader/lib/parser.js:1:80)
    at Module._compile (internal/modules/cjs/loader.js:689:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:700:10)
    at Module.load (internal/modules/cjs/loader.js:599:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:538:12)
    at Function.Module._load (internal/modules/cjs/loader.js:530:3)
    at Module.require (internal/modules/cjs/loader.js:637:17)
    at require (internal/modules/cjs/helpers.js:20:18)

解决：
出现这种错误之后可以使用命令，将vue的版本改成和vue-template-compiler的版本一致，使用命令
npm install vue@2.6.10 --save
