[English](./README.md) | 简体中文

<p align="center">
  <img style='height: auto; width: 80%; object-fit: contain' src="./img/EAF_Banner_Transparent.png">
  <br>新一代的Emacs图形应用框架，通过扩展Emacs的多媒体能力，达到 Live in Emacs 的终极目标
</p>

## 愿景
Emacs距今已经有45年的发展历史，比现在人们用的操作系统都老。在这45年中，全世界最顶级的黑客在贡献自己的智慧和想象力，一起构建了Emacs这个伟大的开发者工具生态。

当你是一个需要使用十几门编程语言的黑客和键盘流信仰者，Emacs绝对是你的不二之选。

Emacs的劣势也是因为它太古老了，导致在多线程和图形扩展能力已经无法跟上时代的步伐，在很多地方发展落后于IDEA和VSCode。

Emacs Application Framework (EAF)的愿景是在保留Emacs古老的黑客文化和庞大的开发者插件生态前提下，通过EAF框架扩展Emacs的多线程和图形渲染能力，实现Live In Emacs的理想。

## 应用列表
EAF是一个可编程扩展的框架，它自带一系列丰富的应用：

| 浏览器                                       | PDF阅读器 |
| :--------:                                       | :----:                                                      |
| <img src="./img/browser.png" width="400"> | <img src="./img/pdf-viewer.png" width="400"> |

| 音乐播放器                       | 文件管理器                         |
| :--------:                                            | :----:                                                |
| <img src="./img/music-player.png" width="400"> | <img src="./img/file-manager.png" width="400"> |
|                                                       |                                                       |

- [Browser](https://github.com/emacs-eaf/eaf-browser): 全功能的网页浏览器，基于Chromium渲染引擎
- [PDF Viewer](https://github.com/emacs-eaf/eaf-pdf-viewer): Emacs里面渲染速度最快的PDF查看器
- [Terminal](https://github.com/emacs-eaf/eaf-terminal): 支持图形绘制的全功能终端模拟器
- [Video Player](https://github.com/emacs-eaf/eaf-video-player): 基于Qt的视频播放器
- [Markdown Previewer](https://github.com/emacs-eaf/eaf-markdown-previewer): Markdown文档实时预览程序，完美兼容Github样式
- [Org Previewer](https://github.com/emacs-eaf/eaf-org-previewer): Org文件实时预览程序
- [Music Player](https://github.com/emacs-eaf/eaf-music-player): 音乐播放器，支持播放列表对齐渲染和实时音频反馈
- [RSS Reader](https://github.com/emacs-eaf/eaf-rss-reader): 新闻阅读器，支持Html内容渲染
- [File Manager](https://github.com/emacs-eaf/eaf-file-manager): 双栏文件管理器，支持文件实时预览
- [Mindmap](https://github.com/emacs-eaf/eaf-mindmap): 全键盘操作的思维导图
- [Jupyter](https://github.com/emacs-eaf/eaf-jupyter): 在Emacs里面运行Jupyter！
- [Image Viewer](https://github.com/emacs-eaf/eaf-image-viewer): 支持实时缩放的图片查看器
- [Camera](https://github.com/emacs-eaf/eaf-camera): 摄像头程序
- [System Monitor](https://github.com/emacs-eaf/eaf-system-monitor): 可视化系统监视器
- [Netease Cloud Music](https://github.com/emacs-eaf/eaf-netease-cloud-music): 网易云音乐前端
- [File Browser](https://github.com/emacs-eaf/eaf-file-browser): 在手机浏览电脑文件
- [File Sender](https://github.com/emacs-eaf/eaf-file-sender): 分享文件给手机
- [Airshare](https://github.com/emacs-eaf/eaf-airshare): 分享文字给手机
- [Demo](https://github.com/emacs-eaf/eaf-demo): EAF的Qt应用实例
- [Vue Demo](https://github.com/emacs-eaf/eaf-vue-demo): EAF的Vue.js应用实例

通过EAF，你可以自由开发自己的Qt5/Vue.js应用并集成在Emacs中。

EAF可以在多个操作系统下工作，包括Linux和Windows，macOS和FreeBSD在beta测试中，部分应用不一定能完美运行。

## EmacsConf2020 - Extend Emacs to Modern GUI Applications with EAF（暂无中文字幕）
EmacsConf2020的[EAF演讲](https://emacsconf.org/2020/talks/34/)。

[![EmacsConf2020 - Extend Emacs to Modern GUI Applications with EAF](https://img.youtube.com/vi/HK_f8KTuR0s/0.jpg)](https://www.youtube.com/watch?v=HK_f8KTuR0s)

## EmacsConf2021 - Emacs Application Framework: A 2021 Update（暂无中文字幕）
EmacsConf2021的[EAF演讲](https://emacsconf.org/2021/talks/eaf/)。

[![EmacsConf2021 - Emacs Application Framework: A 2021 Update](https://img.youtube.com/vi/bh37zbefZk4/0.jpg)](https://www.youtube.com/watch?v=bh37zbefZk4)

## 安装

#### 1. 下载EAF

```Bash
git clone --depth=1 -b master https://github.com/emacs-eaf/emacs-application-framework.git ~/.emacs.d/site-lisp/emacs-application-framework/
```

#### 2. 安装EAF依赖

调用Elisp函数`M-x eaf-install-and-update`或者手动在Terminal跑`install-eaf.py`安装脚本：

```Bash
cd emacs-application-framework
chmod +x ./install-eaf.py
./install-eaf.py
```

`install-eaf.py`脚本有许多有用的选项，可以通过`--help`查看。

#### 3. 加载EAF核心

从这里开始，你可以把EAF加入Emacs的 ```load-path```，然后在 `init.el` 中写入:

```Elisp
(add-to-list 'load-path "~/.emacs.d/site-lisp/emacs-application-framework/")
(require 'eaf)
```
- 如果你使用virtual/conda环境或者想使用`python3`而不是`python`执行命令，请将`eaf-python-command`设成`/usr/bin/python3/`。
- 或者，如果你使用[use-package](https://github.com/jwiegley/use-package)，下面有一个简单的配置文件供你参考:

    ```Elisp
    (use-package eaf
      :load-path "~/.emacs.d/site-lisp/emacs-application-framework" ; Set to "/usr/share/emacs/site-lisp/eaf" if installed from AUR
      :custom
      ; See https://github.com/emacs-eaf/emacs-application-framework/wiki/Customization
      (eaf-browser-continue-where-left-off t)
      (eaf-browser-enable-adblocker t)
      (browse-url-browser-function 'eaf-open-browser)
      :config
      (defalias 'browse-web #'eaf-open-browser)
      (eaf-bind-key scroll_up "C-n" eaf-pdf-viewer-keybinding)
      (eaf-bind-key scroll_down "C-p" eaf-pdf-viewer-keybinding)
      (eaf-bind-key take_photo "p" eaf-camera-keybinding)
      (eaf-bind-key nil "M-q" eaf-browser-keybinding)) ;; unbind, see more in the Wiki
    ```

#### 4. 加载EAF应用

你可以用下面的代码来加载一部分EAF应用，比如浏览器、PDF阅读器和视频播放器，更多的应用请查看 [应用列表](https://github.com/emacs-eaf/emacs-application-framework#applications):

```Elisp
(require 'eaf-browser)
(require 'eaf-pdf-viewer)
```

#### 5. 下载完成！

恭喜，到这一步你已成功下载好了EAF！你可以通过`M-x eaf-open-demo`（前提是你下载了`demo`应用）看看EAF是否可以成功运行了。

如果你有任何使用上的问题，强烈建议读一下[Wiki](#Wiki)以及[常用问题](#常用问题)部分。

建议你时常`git pull` **并且** 运行`install-eaf.py` (`M-x eaf-install-and-update`)来更新各个EAF应用及其依赖。如果使用中遇到任何问题，请先阅读[反馈问题](#反馈问题)部分。

### 依赖列表

| 包名                           | 解释                                     |
| :--------                      | :------                                  |
| python-epc                     | EPC Python端                             |
| python-pyqt5, python-pyqt5-sip | GUI图形库                                |
| python-pyqtwebengine           | 基于Chromium的浏览器引擎                 |
| wmctrl                         | 激活Emacs窗口输入焦点                    |
| pygetwindow                    | 从Windows中eaf激活WSL中Emacs窗口输入焦点 |
| mac-app-frontmost              | 获取macOS当前app名称                     |
| nodejs                         | 下载依赖与应用交互                       |

EAF应用的额外依赖，具体请在其对应的 `app/name/dependencies.json` 和 `app/name/package.json` 中查看。

## EAF应用启动命令
| 应用名称         | 启动命令                                                                    |
| :--------        | :----                                                                       |
| 浏览器           | `M-x eaf-open-browser` 在浏览器中打开或搜索                                 |
|                  | `M-x eaf-open-browser-with-history` 搜索历史或者打开URL                     |
| HTML邮件渲染     | `M-x eaf-open-mail-as-html` 在 `gnus`，`mu4e`，`notmuch` 等邮件客户端中执行 |
| PDF阅读器        | `M-x eaf-open` 输入PDF文件                                                  |
| 视频播放器       | `M-x eaf-open` 输入视频文件                                                 |
| 图片浏览器       | `M-x eaf-open` 输入图片文件                                                 |
| Markdown预览     | `M-x eaf-open` 输入Markdown文件                                             |
| Org预览          | `M-x eaf-open` 输入Org文件                                                  |
| 摄像头程序       | `M-x eaf-open-camera`                                                       |
| 终端模拟器       | `M-x eaf-open-terminal`                                                     |
| 文件管理器  | `M-x eaf-open-in-file-manager`                                         |
| 二维码下载文件   | `M-x eaf-file-sender-qrcode` or `eaf-file-sender-qrcode-in-dired`           |
| 二维码在线浏览器 | `M-x eaf-file-browser-qrcode`                                               |
| 无线分享         | `M-x eaf-open-airshare` 输入要分享给手机的字符串                            |
| 思维导图         | `M-x eaf-create-mindmap` or `M-x eaf-open-mindmap`                          |
| 微软Office阅读器 | `M-x eaf-open-office`                                                       |
| jupyter          | `M-x eaf-open-jupyter`                                                      |
| 音乐             | `M-x eaf-open-music-player`                                                 |
| 系统监视器       | `M-x eaf-open-system-monitor`                                        |
| 演示程序         | `M-x eaf-open-demo`                                                         |
| Vue.js演示程序   | `M-x eaf-open-vue-demo`                                                     |

- EAF浏览器以及PDF浏览器支持Emacs内置书签操作，通过使用`M-x bookmark-set`（默认`C-x r m`）以及`M-x bookmark-bmenu-list`（默认`C-x r l`）。

## 按键绑定

### 全局按键绑定

  | Key   | Event                       |
  | :--   | :--                         |
  | `C-h m` | eaf-describe-bindings       |
  | `C-c b` | eaf-open-bookmark           |
  | `C-c e` | eaf-open-external           |
  | `C-c i` | eaf-import-chrome-bookmarks |
  | `M-/`   | eaf-get-path-or-url         |
  | `M-'`   | eaf-toggle-fullscreen       |
  | `M-[`   | eaf-share-path-or-url       |

### 底部编辑窗口按键绑定

  | Key     | Event                              |
  | :--     | :--                                |
  | `C-c C-c` | eaf-edit-buffer-confirm            |
  | `C-c C-k` | eaf-edit-buffer-cancel             |
  | `C-c C-t` | eaf-edit-buffer-switch-to-org-mode |

## Wiki
强烈建议使用EAF之前浏览一遍[Wiki](https://github.com/emacs-eaf/emacs-application-framework/wiki)。

Wiki囊括了各种你想了解的EAF相关文档，包括了：
1. 按键绑定
2. 自定义选项
3. 架构设计
4. 任务列表

你还会在Wiki发现很多有用的技巧，如Docker，Helm等，

## 常用问题

### EAF是怎么工作的？
<p align="center">
  <img style='height: auto; width: 100%; object-fit: contain' src="./img/framework.png">
</p>

EAF主要实现这几个功能：
1. 利用QWindow的Reparent技术来实现PyQt应用进程的窗口粘贴到Emacs对应的Buffer区域
2. 通过Python EPC来实现Emacs进程和Python进程的控制指令和跨进程消息通讯
3. 通过Qt5的QGraphicsScene来实现镜像窗口，以对应Emacs的Buffer/Window模型

若想了解更多EAF设计背景，请看[Wiki](https://github.com/emacs-eaf/emacs-application-framework/wiki/Hacking)

### EAF vs EXWM?
1. EAF和EXWM的共同点都是：“提升Emacs和别的程序的协作效率“
2. EXWM是一个X11窗口管理器，通过X11协议来控制Emacs和其他程序，但是EXWM只是管理其他程序，但是它并不会修改应用程序的内在行为。
3. EAF不是一个窗口管理器，EAF只是依赖Emacs自身的窗口管理功能显示自己
4. EAF的目标是通过PyQt创造新的应用来扩展Emacs的多媒体能力。从Emacs本身的Buffer/Mode设计上看，它和你平常用的 `xx-mode` 插件没有啥区别，只是它用Qt来绘制内容，而不是Emacs自身的文本库来绘制内容
5. EAF通过造轮子的方式，把大多数程序员常用的应用写出来以后，达到Live in Emacs的最终目标
6. 基于EAF的架构设计，我们可以通过Elisp来控制Python，JavaScript和其他命令行工具，实现多语言扩展Emacs的编程模型。在坚持Emacs黑客文化和Elisp社区兼容性的前提下，让Emacs的多媒体能力能够跟上时代的发展

或许EAF和EXWM看起来有点相似，但它们在设计和理念上是两个完全不同的项目。所以请大家多多学习X11和Qt的区别，理解技术的本质，避免无意义的比较和争论。

### macOS
EAF当前只能部分支持macOS，不是所有功能都可以正常工作，具体的情况请查看[Wiki](https://github.com/emacs-eaf/emacs-application-framework/wiki/macOS)。

### 浏览器崩溃
请不要用pip安装PyQt5, pip的版本有bug，请从操作系统软件仓库安装PyQt5。

### 为什么通过Linux窗口管理器使用EAF无法接收输入信息？
EAF确认可以工作的桌面环境或者窗口管理器包括：KDE、Gnome2、Gnome3、Mate、Xfce、LXDE、Sway、i3、QTile、Xpra、EXWM.

我们认为不同的窗口管理器对于X11协议的支持不够完善才导致这样的问题。

现在的解决方案是将命令`wmctrl -m`中Name的值加入`eaf-wm-focus-fix-wms`，如果还有问题，请在Github提出issue。

### 代理
可以通过下面设置来通过代理访问互联网：

```Elisp
(setq eaf-proxy-type "http")
(setq eaf-proxy-host "127.0.0.1")
(setq eaf-proxy-port "1080")
```

如果你使用Socks5代理，你可以设置代理类型为：

```Elisp
(setq eaf-proxy-type "socks5")
```

基于规则的自定义代理请查看[Wiki](https://github.com/emacs-eaf/emacs-application-framework/wiki/%E8%87%AA%E5%AE%9A%E4%B9%89%E8%A7%84%E5%88%99%E4%BB%A3%E7%90%86)

## EAF社区

下面列表列展示了EAF在Emacs社区的应用。如果我们遗漏你的应用，欢迎提交PR来加到下面列表中。

* ***[obr-viz](https://github.com/swhalemwo/obr-viz)***: visualizing [org-brain](https://github.com/Kungsgeten/org-brain) relationships using EAF
* ***[netease-cloud-music](https://github.com/SpringHan/netease-cloud-music.el)***: A netease music client for emacs.

## 反馈问题

### 反馈安装和配置问题之前，请一定先阅读[Wiki](https://github.com/emacs-eaf/emacs-application-framework/wiki)!!!

如果你使用中遇到任何问题，并且问题是`git pull`后出现的，请先阅读[Mandatory Procedures to Keep Your EAF Up-To-Date](https://github.com/emacs-eaf/emacs-application-framework/discussions/527?sort=new)页面。

关于其他问题，请用命令 `emacs -q` 并只添加EAF配置做一个对比测试，如果 `emacs -q` 可以正常工作，请检查你个人的配置文件。

如果`emacs -q`环境下问题依旧，请到[这里](https://github.com/emacs-eaf/emacs-application-framework/issues/new)反馈, 并附带 `*eaf*` 窗口的内容给我们提交issue，那里面有很多线索可以帮助我们排查问题。。

如果你遇到崩溃的问题, 请用下面的方式来收集崩溃信息:
1. 先安装gdb并打开选项 `eaf-enable-debug`
2. 使用命令 `eaf-stop-process` 停止EAF进程
3. 重新打开EAF, 并在下次崩溃时发送 `*eaf*` 的内容

## 贡献者
<a href = "https://github.com/emacs-eaf/emacs-application-framework/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=emacs-eaf/emacs-application-framework"/>
</a>

## 加入我们
你想把Emacs开发成一个操作系统吗？

想要在Emacs里面生活的更舒适吗？

想要创建下一个激动人心的Emacs插件吗？

[一起疯吧!](https://github.com/emacs-eaf/emacs-application-framework/wiki/Hacking)

## 打赏
如果我的作品让你的生活充满快乐，欢迎请我喝瓶啤酒，哈哈哈哈

### ManateeLazyCat
<p float="left">
    <img src="./img/alipay.jpg" width="188">
    <img src="./img/wechat.jpg" width="200">
</p>
