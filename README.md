## 野火IM解决方案

野火IM是专业级即时通讯和实时音视频整体解决方案，由北京野火无限网络科技有限公司维护和支持。

主要特性有：私有部署安全可靠，性能强大，功能齐全，全平台支持，开源率高，部署运维简单，二次开发友好，方便与第三方系统对接或者嵌入现有系统中。详细情况请参考[在线文档](https://docs.wildfirechat.cn)。

主要包括一下项目：

| [GitHub仓库地址(主站)](https://github.com/wildfirechat)      | [码云仓库地址(镜像)](https://gitee.com/wfchat)        | 说明                                                                                      | 备注                                           |
| ------------------------------------------------------------ | ----------------------------------------------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------- |
| [im-server](https://github.com/wildfirechat/im-server)       | [im-server](https://gitee.com/wfchat/im-server)          | IM Server                                                                                 |                                                |
| [android-chat](https://github.com/wildfirechat/android-chat) | [android-chat](https://gitee.com/wfchat/android-chat) | 野火IM Android SDK源码和App源码                                                           | 可以很方便地进行二次开发，或集成到现有应用当中 |
| [ios-chat](https://github.com/wildfirechat/ios-chat)         | [ios-chat](https://gitee.com/wfchat/ios-chat)         | 野火IM iOS SDK源码和App源码                                                               | 可以很方便地进行二次开发，或集成到现有应用当中 |
| [pc-chat](https://github.com/wildfirechat/vue-pc-chat)       | [pc-chat](https://gitee.com/wfchat/vue-pc-chat)       | 基于[Electron](https://electronjs.org/)开发的PC 端                                        |                                                |
| [web-chat](https://github.com/wildfirechat/vue-chat)         | [web-chat](https://gitee.com/wfchat/vue-chat)         | 野火IM Web 端, [体验地址](http://web.wildfirechat.cn)                                     |                                                |
| [wx-chat](https://github.com/wildfirechat/wx-chat)           | [wx-chat](https://gitee.com/wfchat/wx-chat)           | 小程序平台的Demo(支持微信、百度、阿里、字节、QQ 等小程序平台)                             |                                                |
| [app server](https://github.com/wildfirechat/app_server)     | [app server](https://gitee.com/wfchat/app_server)     | 应用服务端                                                                                |                                                |
| [robot_server](https://github.com/wildfirechat/robot_server) | [robot_server](https://gitee.com/wfchat/robot_server) | 机器人服务端                                                                              |                                                |
| [push_server](https://github.com/wildfirechat/push_server)   | [push_server](https://gitee.com/wfchat/push_server)   | 推送服务器                                                                                |                                                |
| [docs](https://github.com/wildfirechat/docs)                 | [docs](https://gitee.com/wfchat/docs)                 | 野火IM相关文档，包含设计、概念、开发、使用说明，[在线查看](https://docs.wildfirechat.cn/) |                                                |


野火IM VUE Demo，演示如何将野火IM的能力集成到VUE Electron项目。

## 环境依赖
#### mac系统
1. 最新版本的Xcode
2. nodejs v14.18.X
3. npm 6.14.15
4. python 2.7.X
5. git
6. npm install -g node-gyp@8.3.0

#### windows系统
1. nodejs v14.18.X
2. python 2.7.X
3. git
4. npm 6.14.15
5. npm install --global --vs2019 --production windows-build-tools
6. npm install -g node-gyp@8.3.0
> 第5步安装windows开发环境的安装内容较多，如果网络情况不好可能需要等较长时间，选择早上网络较好时安装是个好的选择

#### linux系统
1. nodejs v14.18.X
2. python2.7X
3. git

## 开发
1. ```npm ci```，建议使用华为镜像```npm ci --registry=https://mirrors.huaweicloud.com/repository/npm/```
2. ```npm run dev```

## 打包
打包为当前平台架构软件
```
npm run package
```

## 交叉打包
打包为其它平台架构软件
```
#打包windows系统amd64架构
npm run cross-package-win

#打包windows系统x86架构
npm run cross-package-win32

#打包linux系统amd64架构
npm run cross-package-linux

#打包linux系统arm64架构
npm run cross-package-linux-arm64

#打包mac系统
npm run cross-package-mac
```

## 历史Electron版本
目前master的使用的Electron版本是13.6.9。如果您使用的SDK是8的，请切换到分支[electron_8](https://github.com/wildfirechat/vue-pc-chat/tree/electron_8)。旧版本将进入维护阶段不再添加新的功能，正在开发中的朋友们可以联系我们更新到最新SDK。

## 常见开发问题
1. 如何调试？PC使用了Electron，内嵌Chrome浏览器，跟在浏览器上开发调试是一样的。快捷键Ctrl
+g(MAC下是CMD+g)打开开发者模式。

2. 打包时，如果一直显示```installing production dependencies  platform=win32 arch=ia32 appDir=C:\<your path>\pc-chat\dist```，
   或者提示下载什么之类的，可将```dep```目录下对应平台的electron依赖，解压到对应的目录。
   ```
   // windows
   C:\Users\<你的用户名>\.electron-gyp
   // mac/linux
   ~/.electron-gyp
    ```
3. 打包时，如果下载electron版本超时，可以点[这里](./electron)手动下载electron版本并放到缓存目录。

4. windows上需要严格按照环境进行安装，mac上环境比较简单一些，安装node和node-gyp就可以了
    另外如果还有问题，请试试命令```npm cache clean --force ```，然后删掉node_modules，再重新在非管理员权限下```npm install```

5. 有些杀毒软件会对electron打包的软件报病毒，详情请参考[electron报病毒](https://www.baidu.com/s?wd=electron%20360%E6%8A%A5%E7%97%85%E6%AF%92&pn=0&oq=electron%20360%E6%8A%A5%E7%97%85%E6%AF%92&tn=84053098_3_dg&ie=utf-8&rsv_pq=ec2a876200198701&rsv_t=e981739vB2ZMksgGv8ZOV%2Fb4WIhJDXXzLTfMv24NmIN0itMzRiGjMNnh1qARt19Uzf1s%2FA) 。安装时可能被杀毒软件限制安装，这时候可以让用户使用绿色免安装版（打包后release目录下的unpacked目录）。如果运行时报错，请在杀毒软件里加上例外。另外有条件的公司可以考虑去[360官方](https://open.soft.360.cn)或其他杀软的官方提交检测。

6. ubuntu下，启动时，若提示，```A JavaScript error occurred in the main process Uncaught Exception:Error: Cannot open /opt/wildfirechat/resources/app.asar/marswrapper.node: Error: libdouble-conversion.so.1: cannot open shared object file: No such file or directory```，可安装[libdouble-conversion1](https://packages.debian.org/buster/libdouble-conversion1)解决

7. win平台野火客户端依赖Visual C++ Redistributable Package runtime。如果用户PC上没有安装就需要安装之后才能运行，请从微软官方下载安装
https://www.microsoft.com/zh-CN/download/details.aspx?id=48145 。注意这个安装包是有32位/64位区分的，需要安装对应架构的版本。

8. MAC应用截屏时只能截屏空白桌面，无法截图窗口内容。这是因为没有通过mac系统的安全许可，在设置-》安全与隐私-》切换到隐私那个标签-》屏幕录制-》在野火IM PC应用前打勾，并重启应用。

9. 使用```cnpm```后打包失败，在某些平台```cnpm```是会出现问题的，请使用npm。

10. ```npm install``` 报```Unexpected end of JSON input while parsing near...```错误

    如果常见问题4解决不了，可以尝试```　 npm config set registry http://registry.npm.taobao.org/ ```，然后在按常见问题4的步骤进行

11. 音视频相关问题，请参考以下文档
    1. [av readme](src/wfc/av/internal/README.MD)
    2. [音视频常见问题](https://docs.wildfirechat.cn/faq/webrtc.html?h=webrtc)

12. 纯内网环境，不能显示表情
    1. 将```src/assets/twemoji```目录上传到一个内网能访问的服务器，比如部署```app server```的服务器
    2. 确保通过```http(s)://base_twemoji_url/72x72/1f1e6.png```能访问到对应表情，此处```1f1e6.png```蓝底白字大写字母A
    3. 修改```twemoji.js```，将```https://static.wildfirechat.net/twemoji/assets/```替换成新部署的```http(s)://base_twemoji_url/```，需要注意，最后一个```/```不能省略
    4. 修改```MessageInputView.vue```， 根据新部署的服务器地址，修改正则表达式```replace(/" src="https:\/\/static\.wildfirechat\.net\/twemoji\/assets\/72x72\/[0-9a-z-]+\.png">/g, '')```

13. 想自己部署表情图片
    请常见问题12

14. 一直提示：Electron failed to install correctly, please delete node_modules/electron and try installing again
    1. 尝试执行```node node_modules/electron/install.js```，需要保证网络能畅通访问 github
    2. 如果上一步还是失败的话，请参考[这儿](https://github.com/electron/electron/issues/8466#issuecomment-571425574)

15. windows 7 无法正常启动，显示黑屏或白屏
    1. ```background.js``` 里面找到下面代码，并取消```//app.disableHardwareAcceleration();```前面的注释
    ```
       // pls refer to: https://blog.csdn.net/youyudexiaowangzi/article/details/118676790
       // windows 7 下面，如果启动黑屏，请将下面注释打开
       //app.disableHardwareAcceleration();
    ```
16. MAC打包的版本是Universal版本，可以同时支持x64架构和arm64架构。Universal版本比单架构版本要大一下，如果想要打包单架构的版本，可以把野火SDK瘦身到对应单一架构，然后打包对应平台。具体实现方法请自行查找。

17. MAC系统要求签名才可以运行，有可能需要对野火的SDK重新签名才可以，签名的方法请网络搜索。

18. Linux Arm64版本打包时，在linux+arm64的环境下打包deb格式的版本时会出问题，因为有个依赖软件fpm是x64架构的，必须在x64架构的机器下交叉打包，系统可以是windows/mac/linux都行（mac的arm64机器也可以，因为mac系统有rosetta可以运行x64软件）。

## 截图
![](./image/contact.png)
![](./image/group-conversation-info.png)
![](./image/home.png)
![](./image/picker-user.png)
![](./image/quote.png)
![](./image/sticker.png)


## License

1. Under the Creative Commons Attribution-NoDerivs 3.0 Unported license. See the [LICENSE](https://github.com/wildfirechat/vue-chat/blob/master/LICENSE) file for details.
