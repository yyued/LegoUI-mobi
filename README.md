# LegoUI for Mobile

LegoUI for Mobile 是一套轻量级为移动端而生的前端UI库。把移动端实际项目中较为通用常用的UI组件独立成库，Sass mixin的方式让使用者最大程度上灵活地描绘出自身理想的层叠样式。

---

###使用步骤

1. 基于Lego Mobile基础样式。如果正在使用我们的前端工作流Gulp构建工具 [Generator Lego](https://github.com/duowan/generator-lego)，初始化时选择 `yo lego` mobi分支，则默认已有该基础样式，无需重复导入本库中_base.scss简化基础样式。如果没有使用我们Gulp构建工具，则需导入本库中_base.scss简化基础样式。

2. 在需要使用UI库的sass文件中，导入本库sass文件。如：`@import "_lego";`

3. 在需要使用组件的样式中，导入组件mixin。如：
	
		.ui-window{
			@include ui-window();
		}
		
4. 配合基础html结构，组件基础html结构各有不同，详见 [LegoUI for Mobile]()。如：

		<div class="ui-window">
	       <div class="ui-window__middle">
	           <div class="ui-windowCon">
	               <div class="ui-windowCon__header">标题</div>
	               <div class="ui-windowCon__content">内容</div>
	               <div class="ui-windowCon__footer">
	                   <a href="#"><div class="ui-windowCon__fbtn">取消</div></a>
	                   <a href="#"><div class="ui-windowCon__fbtn">确定</div></a>
	               </div>
	           </div>
	       </div>
	    </div>
	    
---

###组件列表
* 头部
* 列表
* 表单及表单组件（开关，单选，多选等）
* 按钮
* 提示框