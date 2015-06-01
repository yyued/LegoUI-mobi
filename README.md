# [LegoUI for Mobile](http://ued.yypm.com/legomobi/3.0.0/src/docs/home.html)

LegoUI for Mobile 是一套轻量级为移动端而生的前端UI库。把移动端实际项目中较为通用常用的UI组件独立成库，Sass mixin的方式让使用者最大程度上灵活地描绘出自身理想的层叠样式。

## 开始之前

[Sass](https://github.com/sass/sass) 是一种CSS的开发工具，增加了规则、变量、混入、选择器、继承等等特性。

[SeaJS](https://github.com/seajs/seajs) 是一个遵循CommonJS规范的JavaScript模块加载框架。

项目基于 `seajs` 和 `zepto` 进行开发，采用 `sass` 编译环境

## 快速开始

### 1.引入scss

假设你已经安装了sass编译环境，可以通过 [LegoUI-mobi Github](https://github.com/duowan/LegoUI-mobi) 克隆一份`_lego.scss` 文件到你的sass目录下然后用引入该scss，这时候你就可以按需要的使用 每个模块组件的 mixin 例如： `@include mod-popup;`

```scss
// 引入LegoUI-mobi
@import 'lego';
// 引用导航组件mixin
@include mod-popup;
```
**友情提示：如果你还没安装sass，[这里走起](https://github.com/sass/sass)**

### 2.使用seajs

组件依赖 `seajs` , 调用组件前必须引入 `sea-lego.js` 文件

```html
<body>
    ...
    <script src="http://assets.dwstatic.com/mobile/src/js/main/seajs/sea-lego.js" id="seajsnode"></script>
</body>
```

如果你已经在项目中使用了seajs，你可以直接extand一份config配置来使用

```javascript
seajs.config({
    paths: {
        'legoPath': 'http://assets.dwstatic.com/mobile/src/js/',
        'modulePath': 'http://assets.dwstatic.com/legomobi/3.0.0/js/'
    },
    alias: {
        'zepto': 'legoPath/main/zepto/zepto.min.js',
        'touch': 'legoPath/main/zepto/zepto.touch.js',
        'iscroll': 'legoPath/module/iscroll/iscroll.js'
    }
});
```

**注意： `paths` 的配置是依赖必须的， `alias` 中的配置项如果你在项目中已有使用，你可以选择使用自己项目的路径或者使用CDN上的路径**

调用方式1：你可以直接在页面中通过 `seajs.use()` 来调用某个组件，例如：

```html
<script>
    seajs.use(['module/popup'], function(Popup) {
        var popup = new Popup('#popup',{
            hasBg: true,
            hasBgEvent: true,
            hasSelfEvent: true
        });
    });
</script>
```

调用方式2：也可以在自定义的模块中通过 `require` 来调用，例如：

```javascript
define(function(require, exports, module) {
	var Popup = require('modulePath/popup');
	var popup = new Popup('#popup',{
        hasBg: true,
        hasBgEvent: true,
        hasSelfEvent: true
    });
});
```

## 说明文档

低调、绝不华丽的文档展示，[这里走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/home.html)

## 交互组件

### [1.Tab](http://ued.yypm.com/legomobi/3.0.0/src/docs/tab.html)

带过渡效果的Tab面板切换组件，支持手势滑动，[详情走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/tab.html)

### [2.Nav](http://ued.yypm.com/legomobi/3.0.0/src/docs/nav.html)

可以横向滚动的导航条组件，支持缓动、循环、定位，[详情走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/nav.html)

### [3.Falls](http://ued.yypm.com/legomobi/3.0.0/src/docs/falls.html)

两列瀑布流布局实现的组件，支持上拉加载更多，下拉刷新，[详情走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/falls.html)

### [4.Toast](http://ued.yypm.com/legomobi/3.0.0/src/docs/toast.html)

集成了定制文字和图片的仿原生消息提示框组件，[详情走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/toast.html)

### [5.Popup](http://ued.yypm.com/legomobi/3.0.0/src/docs/popup.html)

弹出层组件，可以定制内容及控制方式，[详情走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/popup.html)

### [6.SlideMenu](http://ued.yypm.com/legomobi/3.0.0/src/docs/slidemenu.html)

抽屉式的侧边菜单栏，支持手势事件，[详情走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/slidemenu.html)

### [7.PopupMenu](http://ued.yypm.com/legomobi/3.0.0/src/docs/popupmenu.html)

仿ios原生弹出菜单组组件，可以定制内容及控制方式，[详情走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/popupmenu.html)

### [8.Music](http://ued.yypm.com/legomobi/3.0.0/src/docs/music.html)

支持背景音乐播放的组件，提供默认的控制按钮以及播放控制，[详情走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/music.html)

### [9.Video](http://ued.yypm.com/legomobi/3.0.0/src/docs/video.html)

快速插入视频的组件，通过视频区域控制控制的播放和暂停，[详情走起](http://ued.yypm.com/legomobi/3.0.0/src/docs/video.html)

## UI组件

### [1.按钮](http://ued.yypm.com/legomobi/3.0.0/src/docs/button.html)

在需要使用组件的样式中，导入组件mixin。如：

```scss
.ui-btn{
	@include ui-btn();
}
```

html中使用，如：

```html
<a class="ui-lego ui-btn">按钮样式</a>
```

### [2.头部](http://ued.yypm.com/legomobi/3.0.0/src/docs/header.html)

在需要使用组件的样式中，导入组件mixin。如：

```scss
.ui-header{
	@include ui-header();
}
```

html中使用，如：

```html
<header class="ui-lego ui-header">
    <div class="ui-header__left"></div>
    头部样式
    <div class="ui-header__right"></div>
</header>
```

### [3.列表](http://ued.yypm.com/legomobi/3.0.0/src/docs/list.html)

在需要使用组件的样式中，导入组件mixin。如

```scss
.ui-list{
	@include ui-list();
}
```	

html中使用，如：

```html
<div class="ui-lego ui-list">
    <div class="ui-list__header">列表样式 1</div>
    <ul>
        <li>
            <a href="">item 1</a>
        </li>
        <li>
            <a href="">item 2</a>
        </li>
        <li>
            <a href="">item 3</a>
        </li>
    </ul>
</div>

<div class="ui-lego ui-list">
    <div class="ui-list__header">列表样式 2</div>
    <ul>
        <li class="ui-list__arrow">
            <a href="">item 1</a>
        </li>
        <li class="ui-list__arrow">
            <a href="">item 2</a>
        </li>
        <li class="ui-list__arrow">
            <a href="">item 3</a>
        </li>
    </ul>
</div>

<div class="ui-lego ui-list">
    <div class="ui-list__header">列表样式 3</div>
    <ul>
        <li class="ui-list__shape">
            <a href="">item 1<span class="_shape">2</span></a>
        </li>
        <li>
            <a href="">item 2</a>
        </li>
        <li>
            <a href="">item 3</a>
        </li>
    </ul>
</div>
```

### [4.表单及表单组件（开关，单选，多选等）](http://ued.yypm.com/legomobi/3.0.0/src/docs/form.html)

在需要使用组件的样式中，导入组件mixin。如

```scss	
/* 表单 */
.ui-form{
	@include ui-form();
}

/* 开关 */
.ui-switch{
	@include ui-switch();
}

/* 单选 */
.ui-radio{
	@include ui-radio();
}

/* 复选 */
.ui-checkbox{
	@include ui-checkbox();
}
```	

html中使用，如：

```html
<div class="ui-lego ui-form">

    <div class="ui-form__header">表单样式 1</div>
    
    <div class="ui-form__group">
        <input type="text" placeholder="姓名">
    </div>

    <div class="ui-form__group">
        <input type="password" placeholder="密码">
    </div>

    <div class="ui-form__group ui-form__space">
        <input type="text" placeholder="邮箱地址">
    </div>

    <div class="ui-form__group">
        <input type="text" placeholder="手机号">
    </div>

    <div class="ui-form__group">
        <div class="ui-switch">
            <input type="checkbox">
            <div class="ui-switch__btn"></div>
            <div class="ui-switch__lbl"></div>
        </div>
    </div>

    <div class="ui-form__group">
        <div class="ui-radio">
            <input type="radio" name="sex" checked>
            <div class="ui-radio__lbl">男</div>
        </div>
    </div>
    <div class="ui-form__group">
        <div class="ui-radio">
            <input type="radio" name="sex">
            <div class="ui-radio__lbl">女</div>
        </div>
    </div>

    <div class="ui-form__group">
        <div class="ui-checkbox">
            <input type="checkbox" name="hobby" checked>
            <div class="ui-checkbox__lbl">阅读</div>
        </div>
    </div>
    <div class="ui-form__group">
        <div class="ui-checkbox">
            <input type="checkbox" name="hobby">
            <div class="ui-checkbox__lbl">唱歌</div>
        </div>
    </div>
    <div class="ui-form__group">
        <div class="ui-checkbox">
            <input type="checkbox" name="hobby">
            <div class="ui-checkbox__lbl">跳舞</div>
        </div>
    </div>

    <div class="ui-form__header">表单样式 2</div>
    <div class="ui-form__group2">
        <label>姓名</label>
        <input type="text" placeholder="请输入">
    </div>
    <div class="ui-form__group2">
        <label>密码</label>
        <input type="text" placeholder="请输入">
    </div>
    <div class="ui-form__group2 ui-form__space">
        <label>邮箱地址</label>
        <input type="text" placeholder="请输入">
    </div>
    <div class="ui-form__group2">
        <label>手机号</label>
        <input type="text" placeholder="请输入">
    </div>
</div>			
```

### [5.模态窗](http://ued.yypm.com/legomobi/3.0.0/src/docs/window.html)

在需要使用组件的样式中，导入组件mixin。如：

```scss	
.ui-window{
	@include ui-window();
}
```	

html中使用，如：

```html
<div class="ui-lego ui-window">
    <div class="ui-window__middle">
        <div class="ui-window">
            <div class="ui-window__header">标题</div>
            <div class="ui-window__content">内容</div>
            <div class="ui-window__footer">
                <a href="#"><div class="ui-window__btn">取消</div></a>
                <a href="#"><div class="ui-window__btn">确定</div></a>
            </div>
        </div>
    </div>
</div>
```	

## 更新说明

* 1.0 基础版本。 
* 1.1 加入.ui-lego命名空间，直接使用无需引入_base.scss基础样式文件。
