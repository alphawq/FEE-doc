---
title: Client端
date: 2020-03-20
author: Aphasia
# layout: SpecialLayout
---

# 项目介绍 <Badge text="beta" type="warning"/> <Badge text="默认主题"/>

本项目为灯塔前端项目.

最低支持的屏幕分辨率: 1440 \* 900

# Todo List

-[X] 引入 webpack 打包配置 -[ ] 引入 babel 转义 -[ ] eslint 切换到 jsStandard 规范 -[ ] 完善 jsconfig, 支持 vue -[ ] 在 readme 中添加使用说明 -[ ] 在 readme 中添加 npm 使用说明 -[X] 在 readme 中添加项目发布流程

# npm 包使用说明

```bash

webpack         项目打包配置
webpack-cli

shelljs         执行shell命令
ora             打印spinner效果
chalk           打印日志

#   webpack常用组件
extract-text-webpack-plugin
webpack-uglify-parallel
copy-webpack-plugin
extract-text-webpack-plugin
file-loader
friendly-errors-webpack-plugin
html-webpack-plugin
optimize-css-assets-webpack-plugin
style-loader
url-loader

vue-loader
vue-style-loader
vue-template-compiler
webpack-merge
webpack-bundle-analyzer
webpack-dev-middleware
webpack-hot-middleware

#   babel转义
babel-loader@8
@babel/core
@babel/preset-env

```

## Install

```bush
// install dependencies
npm install
```

## Run

### Development

```bush
npm run dev
```

### Production(Build)

```bush
npm run build
```

### 项目发布

首先在本地执行`cat ~/.ssh/id_rsa.pub`, 记下 ssh 公钥
登陆相应环境
执行下方命令, 将公钥添加到服务器上

```bash
echo '公钥内容' >> ~/.ssh/authorized_keys
```

测试环境:
部门开发机环境:
备用环境:

```bash
#   发布dev环境代码
npm install                                                             \
&& npm run build                                                        \
&& echo "publish fe resource to "                          \
&& scp -r ./dist/* root@*****/fee-rd/public/  \
&& echo "publish success"
```

```bash
#   发布testing环境代码
npm install                                                            \
&& npm run build                                                       \
&& echo "publish fe resource to "                           \
&& scp -r ./dist/* root@*****/fee-rd/public/   \
&& echo "publish success"

```

```bash
#   发布bak环境代码
npm install                                                            \
&& npm run build                                                       \
&& echo "publish fe resource to "                           \
&& scp -r ./dist/* root@*****/fee-rd/public/   \
&& echo "publish success"

```

## 项目功能

- 注册
- 登录
  - 普通用户登录(需要先注册)
  - 内部用户登录
- 修改信息(普通用户)
  - 修改昵称
  - 修改密码
- 登出
  - 注销账号(普通用户)
  - 退出登录
- 权限
  - 用户
    - admin( 拥有所有项目权限,以及项目成员管理权限)
    - dev(普通用户)
  - 项目成员
    - owner(拥有项目成员管理权限)
    - dev(普通开发者)
- 切换项目(当前登录用户参与的项目)
- 用户行为
  - 菜单点击量
  - 用户在线时长
  - 新增用户数据
- 异常监控
- 报警
  - 配置( 设置报警条件,通过邮件或企微发送报警信息)
  - 日志(报警历史记录)
- 埋点测试(用于测试环境,检测打点数据是否能正常收到)
- 成员管理(owner 权限)
  - 添加成员
  - 修改成员  角色(只能是'owner'或'dev')
  -  修改是否发送报警 

---

## 文件结构

```shell
.
├── build  项目构建配置
├── config  开发相关配置
├── public  打包所需静态资源
└── src
    ├── api  AJAX请求
    └── assets  项目静态资源
        ├── icons  自定义图标资源
        └── images  图片资源
    ├── components  业务组件
    ├── config  项目运行配置
    ├── directive  自定义指令
    ├── libs  封装工具函数
    ├── router  路由配置
    ├── store  Vuex配置
    ├── view  页面文件
    └── tests  测试相关
```

# 发布脚本

```
npm run build

scp -r /Users/wiszc/code/plat-fe/fee-fe/dist/. root@*****/fee-rd/public/.

scp -r /Users/wiszc/code/plat-fe/fee-fe/dist/index.html root@1*****/fee-rd/dist/views/index.ejs

ZjZiNzc0ZjY3MmUyZGJjMjhhNDcxOWMw
```

# DEPENDENCIES INTRODUCE

## [@antv](https://antv.alipay.com/zh-cn/index.html)

AntV 是蚂蚁金服全新一代数据可视化解决方案。AntV 数据可视化设计原则是基于 [Ant Design](https://ant.design/docs/spec/introduce-cn) 设计体系衍生的，具有数据可视化特性的指导原则。它遵循 Ant Design 设计价值观的同时，对数据可视化领域的进一步解读，如色彩、字体的指引。

## [axios](https://github.com/axios/axios)

很好用的 http 请求库

## [codemirror](https://codemirror.net)

CodeMirror 是一个用 JavaScript 实现的多功能文本编辑器。它专门用于编辑代码，并带有许多语言模式和插件 ，可实现更高级的编辑功能。

## [countup](https://github.com/inorganik/countUp.js#readme)

CountUp.js 是一个无依赖，轻量级的 JavaScript“类”，可用于快速创建以更有趣的方式显示数字数据的动画。

## [cropperjs](https://fengyuanchen.github.io/cropperjs)

javascript 图像裁剪器

## [echarts](http://echarts.apache.org)

ECharts，一个使用 JavaScript 实现的开源可视化库，可以流畅的运行在 PC 和移动设备上，兼容当前绝大部分浏览器（IE8/9/10/11，Chrome，Firefox，Safari 等），底层依赖轻量级的矢量图形库 ZRender，提供直观，交互丰富，可高度个性化定制的数据可视化图表。

## [html2canvas](https://html2canvas.hertzen.com)

该脚本允许您直接在用户浏览器上截取网页或部分网页的“屏幕截图”。

## [iview](http://www.iviewui.com)

iView 是一套基于 Vue.js 的开源 UI 组件库，主要服务于 PC 界面的中后台产品。提供了高质量、功能丰富友好的 API ；自由灵活地使用空间；细致的 UI；事无巨细的文档；可自定义主题

## [iview-area](https://github.com/iview/iview-area#readme)

一款基于 Vue 框架和 iView-UI 组件库开发的城市级联组件，数据包含中国的省(直辖市)、市、县区和乡镇街，数据来源 area-data

## [js-cookie](https://github.com/js-cookie/js-cookie#readme)

一个简单，轻量级的 JavaScript API，用于处理 cookie

## [lodash](https://lodash.com/)

一个现代 JavaScript 实用程序库，提供模块化，性能和附加功能。提供了常用的比如 get(从指定对象获取制定属性)，has(判断指定对象是否有某些属性)，set(给指定对象设置属性)

## [moment](http://momentjs.com)

是一个用于在 Javascript 中处理日期和时间的库。特征：DateTime，Duration 和 Interval 类型；不可变的，可链接的，明确的 API；常见和自定义格式的解析和格式化；本机时区和 Intl 支持（没有语言环境或 tz 文件）。

## [sortablejs](https://github.com/rubaxa/Sortable#readme)

Sortable 是一个用于可重新排序的拖放列表的 JavaScript 库。特征：支持触摸设备和现代浏览器（包括 IE9）；可以从一个列表拖动到另一个列表或在同一列表中；移动项目时的 CSS 动画；支持拖动手柄和可选文本（优于 voidberg 的 html5sortable）；智能自动滚动；使用原生 HTML5 拖放 API 构建。

## [v-charts](https://v-charts.js.org)

在使用 echarts 生成图表时，经常需要做繁琐的数据类型转化、修改复杂的配置项，v-charts 的出现正是为了解决这个痛点。基于 Vue2.0 和 echarts 封装的 v-charts 图表组件，只需要统一提供一种对前后端都友好的数据格式设置简单的配置项，便可轻松生成常见的图表。

## [viser-vue](https://github.com/viserjs/viser)

适用于基于 G2 的数据可视化工具的工具包。Viser 支持 React，Vue 和 AngularJS。特征：只需使用带有图表的语义组件进行部署，包括但不限于 React，Vue 和 AugularJS；轻量级仅依赖于 G2，这是一个基于图形语法的 Javascript 绘图系统。

## [vue](https://github.com/vuejs/vue#readme)

## [vue-i18n](https://github.com/kazupon/vue-i18n#readme)

Vue I18n 是 Vue.js 的国际化插件。它可以轻松地将一些本地化功能集成到您的 Vue.js 应用程序中。功能包括：各种格式本地化；多元化；DateTime 本地化；号码本地化；基于组件的本地化；分量插值；后备本地化。特征：您可以使用简单的 API 将国际化引入您的应用；除了简单的翻译外，还支持多元化，数字，日期时间等本地化等；您可以在单个文件组件上管理区域设置消息

## [vue-router](https://github.com/vuejs/vue-router#readme)

vue-router 是 Vue.js 的官方路由器。它与 Vue.js 核心深度集成，使用 Vue.js 构建单页应用程序变得轻而易举。功能包括：嵌套路由/视图映射；模块化，基于组件的路由器配置；路线参数，查询，通配符；查看由 Vue.js 过渡系统提供支持的过渡效果；细粒度的导航控制；与自动活动 CSS 类的链接；HTML5 历史模式或哈希模式，在 IE9 中具有自动回退功能；可自定义的滚动行为。

## [vuex](https://github.com/vuejs/vuex#readme)

Vue.js 的集中状态管理

## [wangeditor](http://wangeditor.github.io/)

基于 javascript 和 css 开发的 Web 富文本编辑器， 轻量、简洁、易用。

## [xlsx](http://sheetjs.com/opensource)

各种电子表格格式的解析器和编写器。来自官方规范，相关文档和测试文件的 Pure-JS cleanroom 实现。强调解析和编写健壮性，跨格式功能与统一的 JS 表示兼容，以及 ES3 / ES5 浏览器与 IE6 的兼容性。

# 项目说明

## 登陆

登陆地址 => http://test-arms.example.com/login

使用账号&密码进行登陆.

![登陆截图](http://ww1.sinaimg.cn/large/6671cfa8ly1fxlllzwuzmj21hc0qcqv7.jpg)

## 使用

登陆后默认进入 saas 项目, 随后可以让管理员把自己加到对应项目里.

平台按项目进行查看, 提供以下功能

- 用户行为
  - 操作系统分布
  - 浏览器版本分布
  - 新增用户
  - 菜单点击量
  - 用户在线时长
- 异常监控
  - DashBoard
  - js 异常
  - 页面性能
  - HTTP CODE
  - 接口数据结构
  - 启动过程
  - 加载页面失败
  - 登录异常
  - 代理异常
- 埋点测试
  - 面向测试、开发人员，单纯测试打点链路是否可行,以及测试打点数据的展示。
- 成员管理
  - 面向项目 owner，可由 owner 添加,删除成员，或者修改成员角色
  - 成员管理中可以配置是否订阅项目报警信息, 默认不订阅
- 报警配置
  - 可以设定错误触发阈值, 错误数超出阈值后即会在企业微信中发送报警消息

# 组件 CheckList

-[ ] style 是否已添加 scoped 属性

# VSCode 前端格式化推荐配置

##安装 eslint,vetur 插件 ##点击设置->搜索 settings.json，将如下配置填入进去

```json
   // eslint配置
   "eslint.autoFixOnSave": true,
   "eslint.options": {
     "extensions": [
       ".html",
       ".js",
       ".vue",
       ".jsx"
     ]
   },
   "eslint.validate": [
     {
       "language": "html",
       "autoFix": true
     },
     {
       "language": "vue",
       "autoFix": true
     },
     {
       "language": "javascript",
       "autoFix": true
     },
     {
       "language": "javascriptreact",
       "autoFix": true
     }
   ],

```

#debug 开关

```
开发模式可用debug.js修改服务器，端口号，从Git上克隆时有debug.js_,改成.js即可
```
