---
id: getting-started
title: Getting Started
layout: docs
category: Quick Start
permalink: docs/getting-started.html
next: tutorial
---

## Requirements

1. OS X - This repo only contains the iOS implementation right now, and Xcode only runs on Mac.
2. New to Xcode?  [Download it](https://developer.apple.com/xcode/downloads/) from the Mac App Store.
3. [Homebrew](http://brew.sh/) is the recommended way to install node, watchman, and flow.
4. `brew install node`. New to [node](https://nodejs.org/) or [npm](https://docs.npmjs.com/)?
5. `brew install watchman`. We recommend installing [watchman](https://facebook.github.io/watchman/docs/install.html), otherwise you might hit a node file watching bug.
6. `brew install flow`. If you want to use [flow](http://www.flowtype.org).

## Quick start

- `npm install -g react-native-cli`
- `react-native init AwesomeProject`

In the newly created folder `AwesomeProject/`

- Open `AwesomeProject.xcodeproj` and hit run in Xcode
- Open `index.ios.js` in your text editor of choice and edit some lines
- Hit cmd+R ([twice](http://openradar.appspot.com/19613391)) in your iOS simulator to reload the app and see your change!

Congratulations! You've just successfully run and modified your first React Native app.


# 新手上路

## 系统要求

1. OS X，目前仅包含了iOS的实现，Xcode只在Mac上才能运行
2. 开发者可以从Mac应用商店[下载Xcode](https://developer.apple.com/xcode/downloads/)
3. [Node](https://nodejs.org/)或者[npm](https://docs.npmjs.com/)的新手可以通过`brew install node`来安装Node.js
4. `brew install watchman`. 我们建议安装[watchman](https://facebook.github.io/watchman/docs/install.html)，否则你可能会遇到`node`的文件监控bug
5. 如果你想使用[flow](http://www.flowtype.org/)，可以通过`brew install flow`

## 快速上路

- `npm install -g react-native-cli`
- `react-native init AwesomeProject`

在`AwesomeProject/`目录中执行如下操作：

- 打开`AwesomeProkect.xcodeproj`，然在在`Xcode`中点击`run`运行
- 用文本编辑器打开`index.ios.js`，编辑一些代码
- 在iOS simulator中按cmd + R([twice](http://openradar.appspot.com/19613391))来重载APP，并且观察之前的改动

恭喜！您刚刚成功的运行并且编写了您第一个React Native应用。

## 备注

额外有一步操作在官方文档中没有体现，否则会运行失败。具体如下，两种方式任选一种：

打开项目中的`AppDelegate.m`
- 方式一：找到这行代码：jsCodeLocation = [NSURL URLWithString:@"http://`localhost`:8081/index.ios.bundle"]，将localhost换成自己的ip
- 方式二：
  - 注释掉方式一中的代码
  - 去掉`jsCodeLocation = [[NSBundle mainBundle] URLForResource:@"main" withExtension:@"jsbundle"];`前面的注释。
  - run `npm start`
  - run `curl http://localhost:8081/index.ios.bundle -o main.jsbundle` 如果失败的话在后面加上`--ipv4`
  - 在XCode中，右击你的项目文件夹，点击`New file`，选择你生成的`main.jsbundle`。
- 推荐第一个方法比较简单。
- 现在就可以在无服务器的环境下运行你的app啦。
