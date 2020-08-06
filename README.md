> NSIS_SetupSkin 基于 [nsNiuniuSkin](http://www.ggniu.cn/download.htm) 的个性化打包工具

# NSIS_SetupSkin

> 通过 [NSIS_SetupSkin](https://github.com/woytu/NSIS_SetupSkin) 修改而来，其中借鉴了该项目的文件结构思想和使用说明文档

> 该安装包界面控件是一个可集成于NSIS的插件，采用Duilib开发，在使用时，安装包制作者只需要做如下两件事情：
>> 1. 通过配置Duilib的资源，设计好界面显示的元素

>> 2. 在NSIS的脚本中，通过NSIS脚本调用nsNiuniuSkin.dll的相关接口，集成UI及安装包的业务功能 

> 在控件的资源中，采用的是通过TAB控件来实现不同阶段的安装界面，比如：选择路径、许可协议、安装进度、完成、卸载等，在实际使用中，通过NSIS脚本来设置当前需要显示的TAB页，即可完美的呈现出需要的界面UI了。



* [使用方法](/使用方法.md)

* [api](/api.md)



## NSIS

* [https://sourceforge.net/projects/nsis](https://sourceforge.net/projects/nsis)
* [https://nsis.sourceforge.io/Category:Plugins](https://nsis.sourceforge.io/Category:Plugins)

* [https://sourceforge.net/projects/hmne](https://sourceforge.net/projects/hmne)
* [http://hmne.sourceforge.net](http://hmne.sourceforge.net)


## 关于nsNiuniuSkin License

* [http://www.ggniu.cn/articles/nsniuniuskin.html](http://www.ggniu.cn/articles/nsniuniuskin.html)

> nsNiuniuSkin是目前国内最专业的安装包UI控件，与NSIS完美融合。同时它也是一个**完全免费**的安装包UI控件，无任何的使用限制。我们的目标是让稍微有一点NSIS基础的人在一天内完成一个安装包制作。



**下载软件目录包：**

* [https://www.woytu.com/?dir=PacketTool/software-pkg](https://www.woytu.com/?dir=PacketTool/software-pkg)

* [https://gd.woytu.workers.dev/file/PacketTool/software-pkg/](https://gd.woytu.workers.dev/file/PacketTool/software-pkg/)

* [https://yinkss-my.sharepoint.com/:f:/g/personal/claer_simplove_eu_org/En4SJNSpmnpEjKiuwfVW2wYBJEuUCtF8p5gjA970Y2qK8Q](https://yinkss-my.sharepoint.com/:f:/g/personal/claer_simplove_eu_org/En4SJNSpmnpEjKiuwfVW2wYBJEuUCtF8p5gjA970Y2qK8Q)


## 目录结构

```
.
│  7z.dll                                   7z压缩dll
│  7z.exe                                   7z压缩主程序
│  makeapp.bat                              压缩FilesToInstall文件夹脚本
│  makensiscode.bat                         不压缩时遍历FilesToInstall文件夹生成编译需要的app.nsh文件
│  makeskinzip.bat                          压缩SetupScripts/*/skin文件夹
│  
├─FilesToInstall                            源程序文件夹
├─NSIS                                      NSIS主程序文件夹
├─OriginPlugin                              插件
└─SetupScripts                               项目UI配置目录
    │  commonfunc.nsh                        公共函数
    ├─nim                                    无复选框UI示例
    │  │  build-nim-nozip.bat                 不带压缩构建脚本
    │  │  build-nim.bat                       带压缩构建脚本
    │  │  licence.rtf                         产品许可文件
    │  │  license.txt
    │  │  logo.ico                            产品logo图标
    │  │  nim.nsi                             安装包产品信息定义,引用了ui.nsh
    │  │  ui.nsh                              UI函数
    │  │  uninst.ico                          卸载图标
    │  │  
    │  └─skin                                 UI配置
    │      │  configpage.xml                    配置页XML
    │      │  default.xml                       全局XML
    │      │  finishpage.xml                    安装完成页XML
    │      │  install.xml                       安装首页XML
    │      │  installingpage.xml                安装进行页XML
    │      │  licensepage.xml                   产品许可页XML
    │      │  msgBox.xml                        提示消息页XML
    │      │  uninstallfinishpage.xml           卸载完成页XML
    │      │  uninstallingpage.xml              卸载进行页XML
    │      │  uninstallpage.xml                 卸载首页XML
    │      │  
    │      ├─form                             公共文件，比如公用图片
    │      └─public                           独立部件文件
    │          ├─bk
    │          ├─button
    │          ├─caption
    │          ├─checkbox
    │          ├─edit
    │          └─vsrcollbar
    │                  
    └─songliwu                                   有复选框UI示例
        │  build-songliwu-nozip.bat              不带压缩构建脚本
        │  build-songliwu.bat                    带压缩构建脚本
        │  license.txt                           产品许可文件
        │  logo.ico                              产品logo图标
        │  songliwu.nsi                          安装包产品信息定义,引用了ui.nsh
        │  ui.nsh                                UI函数
        │  uninst.ico                            卸载图标
        │  
        └─skin                                 UI配置
            │  configpage.xml                    配置页XML
            │  default.xml                       全局XML
            │  finishpage.xml                    安装完成页XML
            │  install.xml                       安装首页XML
            │  installingpage.xml                安装进行页XML
            │  licensepage.xml                   产品许可页XML
            │  msgBox.xml                        提示消息页XML
            │  msgBox2.xml
            │  uninstallfinishpage.xml           卸载完成页XML
            │  uninstallingpage.xml              卸载进行页XML
            │  uninstallpage.xml                 卸载首页XML
            │  
            └─form                             公共文件，比如公用图片
```