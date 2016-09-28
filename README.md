# stuq-wxapp：狼叔带你一起玩转微信应用号


主题：微信小程序开发适合你吗？

## 微信小程序是什么？

（从技术角度看，微信提供的框架、接口、开发方法）

微信小程序是限于微信提供的MINA框架提供的app开发便捷展示解决方案

## IDE


helper for https://github.com/gavinkwoe/weapp-ide-crack

第一批内测只有200个，所以大部分人都没办法弄到，但又想提前体验，怎么办呢？

先从 https://github.com/gavinkwoe/weapp-ide-crack 开始说起吧。

### gavinkwoe是谁？

gavinkwoe是郭虹宇，老郭以前在腾讯，后来出来在呼家楼那边创业，很棒的公司，他本人技术也是相当到位的，最早是beeframework，代码写的还是相当棒，这货对tcp和c也相当厉害，据说拿过专利。后来bee半火不火的，就搞了类似于css描述生成iOS页面的东西，之后react-native出来之后，貌似就转rn了。而且还带出了QFish这样的优秀小弟，很棒的。

总之，老郭有非常强大的iOS开发能力，所以这次破解微信开发工具也是有一定必然性的。

### 小助手：weide

https://github.com/i5ting/weide

它其实就为了简化安装破解而写的简单小程序。利用node模块和npm强大的机制，简化破解并提供实用辅助功能。特别简单，但还算实用。

### 安装小助手

```
$ [sudo] npm i -g weide
```

### 小助手用法

- 下载微信web开发者工具0.9(百度: https://pan.baidu.com/s/1pLxqFzH （密码: bwt9）) 位置 /Applications/微信web开发者工具.app/
- 下载微信web开发者工具0.7(百度: https://pan.baidu.com/s/1pLTKIqJ （密码: iswg）) 位置 /Applications/微信web开发者工具0.7.app/

如果开发工具安装目录是/Applications/微信web开发者工具.app/，无需配置，一条命令即可

```
$ weide
```

否则需要配置环境变量


mac

```
$ export WECHAT_IDE=/Applications/微信web开发者工具0.9.app/
$ weide
```

windows cmd

```
$ set WECHAT_IDE=/Applications/微信web开发者工具0.9.app/
$ weide
```

### 项目创建

用法部分来自老郭 http://www.geek-zoo.com

1. 运行『微信Web开发者工具』
2. 通过微信扫描二维码
3. 创建项目
  * AppID：随便填
  * 项目名称：随便填
  * 本地开发目录：选择一个目录
4. 点击「添加项目」
  * 此时如果出错，先退出再重进
  * 此时，能够看到项目列表了
5. 打开项目
6. 开始开发
7. Good luck

### 学习资料

* NoteDown版本
	* 框架入门
		* http://wxopen.notedown.cn/framework/MINA.html
	* 组件入门
		* http://wxopen.notedown.cn/component/
	* API入门
		* http://wxopen.notedown.cn/api/

### Demo运行

* 创建项目
* 打开项目所在目录
* 下载「Demo源代码」并解压覆盖
* 打开项目
* Good luck

### 常见问题

1. 找不到所要替换的文件
  * 问题原因：开发工具版本不正确，老版本不支持
  * 解决方案：确保下载的程序版本在0.9.092100以上
2. Failed to load resource: net::ERR_NAME_NOT_RESOLVED http://1709827360.appservice.open.weixin.qq.com/appservice
  * 问题原因：通常是由于系统设置了代理如Shadowsocks等。
  * 解决方案：关闭代理，或者依次点击工具栏“动作”-"设置"，选择“不使用任何代理，勾选后直连网络”。
3. 修复asdebug.js报错
  * 问题原因：TypeError: Cannot read property 'MaxRequestConcurrent' of undefined
  * 解决方案：替换 /Resources/app.nw/app/dist/weapp/appservice/asdebug.js  
4. 扫码登录失败
  * 问题原因：please bind your wechat account to the appid first
  * 解决方案：先使用0.7版本的进行扫码登陆，登陆成功后，再用0.9的版本打开就直接进入了。
    * 0.7版本地址：http://dldir1.qq.com/WechatWebDev/release/0.7.0/wechat_web_devtools_0.7.0.dmg
5. mac版本升级到0.9.092300后，asdebug.js报错
  * 问题原因：TypeError: Cannot read property 'MaxRequestConcurrent' of undefined
  * 解决方案：替换 /Resources/app.nw/app/dist/weapp/appservice/asdebug.js  

### 工具截图

![IDE](https://cloud.githubusercontent.com/assets/876707/18745196/f4f0488e-80f3-11e6-844b-f45d7e52a23c.png)

![IDE](https://cloud.githubusercontent.com/assets/876707/18745200/f7a74870-80f3-11e6-83cf-df00f7f87f56.png)

### 禁用自动升级

破解之后，微信官方立马2个通宵，修复了大量问题，包括store命名错误，自动升级。可以说之前的版本是没有被特意“保护”的，所以可以挖出更多细节，nw.js的升级机制很简单，非常容易破解

```
$ wecrack
```

会修改Contents/Resources/app.nw/package.json的版本号，避免自动升级

### 一键美化压缩js代码

会读取默认安装位置，或环境变量里的WECHAT_IDE下的所有js都会美化

```
$ allb
```

### 调试

```
$ DEBUG=weide weide
```


## 实例：用cnode社区api做微信小应用


https://github.com/coolfishstudio/wechat-webapp-cnode

### 导入项目

添加项目

![1](images/import/1.png)


选择源码所在目录

![2](images/import/2.png)

完整信息

![3](images/import/3.png)



1. 
2. 微信小程序开发需要具体哪些技术知识？

- 会js、css
- 理解移动端h5相关开发概念
- 使用微信提供的wxml和wxss
- 熟悉微信提供api
- 熟悉http协议

3. 适合0基础的前端工程师学习？

和h5类似，入门简单，精通很难

4. 微信小程序跟HTML5、Web APP的关系

- 小程序不是HTML5，也不是Web APP
- 都是展示层的
- 基础知识都是一样的，移动端，http协议等
- api和开发方式有一定差异，都属于受限开发
- 小程序的抽象程度更高，与是h5实现还是native实现无关
- 和Web App关系不大，但会Web App学这个还是比较容易的

5. 微信小程序demo （如果有）

6. 怎么学习微信小程序，如果没有邀请码，可以怎么学？

狼叔带你一起玩破解，微信开发工具升级也不怕

7. 推荐Nodejs微信开发的课

小程序只是增加了一种选择，以前是h5，pc，app，现在是小程序，h5，pc，app，它们无疑都是展示层的实现，所以对后台是没有影响的。它们的共性是会js能让你开发的更好，而今Node.js凭借其性能和强大npm生态，以及在大前端的火爆，使得Node.js无处不在。

在这种情况下使用Node.js开发微信相关功能是非常好的选择，成本最低，可以获得相对不错的性能，而且易于扩展。

StuQ的《Nodejs微信开发》课程深入浅出，通过Node.js和express框架，微信三大功能分享，授权，支付，以及h5+weui实践，给你一个不一样的实用技能。

最近《Nodejs微信开发》会继续深入，增加小程序开发部分，敬请期待

8. 推荐一些学习资料

参见 https://github.com/justjavac/awesome-wechat-weapp


前端4阶段

- 原始
- jquery
- angular，bb
- react。vue 

推荐给雷蒙德的可选课程

- jquery  + bootstrap + 后台开发（难度较低，适合那些偏java的人）
- angularjs2 + ionic 2 （难度较大，ng2刚发布，需要学ts，另外里面概念非常多）
- vue 2、weex（刚发布不久，无论推广还是趋势都不错）
- react和rn（依然很拉风）
- 高效前端工具集webpack，gulp，npm，postcss，less，coffee （比较零散，但可以提高视野，在工作中可能会用上）
- h5 + cordova + weui + vux（移动端一些比较好的集合）
- nw.js + react 或 electron + react 构建PC桌面应用（钉钉、微信工具ide等把pc端桌面使用web技术构建推向高潮）
- 七周七个前端开源项目（精选，和高效前端工具集类似）
- koa2.0 （node7月底发布，支持async/await开始大推）




## 关于StuQ

![](images/stuq.png)

软件公司招聘需要巨大，但入门难，技术发展过快（指数），而人的曲线成长较慢，现在的慕客形式又过于老旧，呆板，少互动，所以社群时代的在线教育，一定是专业的、互动的、深入浅出、共同成长，这些正是StuQ最擅长的方面，我个人特别看好StuQ这个品牌，真心推荐，如果不是股份绑定，我一定会加入StuQ
