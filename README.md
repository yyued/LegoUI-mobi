# [LegoUI for Mobile](http://ued.yypm.com/legomobi/3.0.0/src/docs/home.html)

LegoUI for Mobile 是一套轻量级为移动端而生的前端UI库。把移动端实际项目中较为通用常用的UI组件独立成库，Sass mixin的方式让使用者最大程度上灵活地描绘出自身理想的层叠样式。

---

###使用步骤

1. 在需要使用UI库的sass文件中，导入本库sass文件。如：`@import "lego";`

2. 在需要使用组件的样式中，导入组件mixin。如：
	
		.ui-header{
			@include ui-header();
		}
		
3. 配合基础html结构，组件基础html结构各有不同，详见 [LegoUI for Mobile](http://ued.yypm.com/legomobi/3.0.0/src/docs/home.html)。如：

		<header class="ui-header">
	        <div class="ui-header__left"></div>
	        头部样式
	        <div class="ui-header__right"></div>
	    </header>
	    
---

###UI组件列表
* 按钮
* 头部
* 列表
* 表单及表单组件（开关，单选，多选等）
* 模态窗

---

###交互组件
详见 [LegoUI for Mobile](http://ued.yypm.com/legomobi/3.0.0/src/docs/home.html)。

---

###更新说明
* 1.0 基础版本。
* 1.1 加入.ui-lego命名空间，直接使用无需引入_base.scss基础样式文件。