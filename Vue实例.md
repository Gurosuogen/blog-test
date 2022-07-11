## Vue实例 
### 使用codesandbox快速创建vue项目
1. 进入`codesanbox.io`
2. 点击右上角的的`create sanbox`
3. 选择vue3
4. 开始写代码

### vue.js 和 vue.runtime.js的区别
- [参考](https://juejin.cn/post/6950456847048376334)
- vue.js
	- 完整版 = 运行时版+编译器（编译器：将模板字符串编译成为JS渲染函数的代码）
	- 可直接将内容写在HTML中查看视图效果，或用`template` 渲染到 HTML
	- webpack引入，需要配置alias，@vue/cli 引入也需要额外配置
- vue.runtime.js
	- 无编译器,故占用代码体积小
	- 无法直接实现页面渲染，需要利用`render`里的 h 函数来创建 HTML 节点。h就是vue.runtime.js提供的函数，它接收模版字符串中的参数，返回渲染好的原始的html
	- vue.js的webpack引入和@vue/cli 引入都默认使用此版本
- 总结
	- `完整版`可以将代码写到HTML或者template选项里
	- `完整版`可直接将内容写在HTML中查看视图效果，或用template渲染到HTML
	- `运行时版`无法直接实现页面渲染，需要利用 render 里的 h 函数来创建 HTML 节点，vue.js的webpack引入和@vue/cli 引入都默认使用此版本
	- `运行时版`一般配合webpack的`vue-loader`使用
	- 默认使用`运行时版`
		1. 保证用户体验，用户下载的JS文件提及更小，`但只支持h函数`
		2. 保证开发体验，开发者可直接在vue文件里写HTML标签，`而不写h函数`
		3.  使用vue-loader把vue文件里的HTML`转为h函数`
### template 和 render
- template
	- 使用html的方式渲染
	- 类型：字符串
	- 在字符串模板中的内容会替换HTML中被`挂载`的元素
	- 示例
	```js
	<template>
		<div id="app">
	    {{n}}
	    <button @click="add">+1</button>
		</div>
	</template>
	```
- render
	- 使用JS的方式渲染
	- 类型：函数
	- 接受一个回调函数h，返回标签名和标签内容
	- 示例
	```js
	render(h){ 
		return h('div', [this.n,h（'{on:{click:this.add}’,'+1'])
	}
	```

### Vue-Loader和单文件组件
- [Vue Loader](https://vue-loader.vuejs.org/zh/) 是一个 webpack的 loader，它允许你以一种名为[单文件组件 (SFCs)](https://vue-loader.vuejs.org/zh/spec.html)的格式撰写 Vue 组件
- 单文件组件简介
	- `.vue` 文件是一个自定义的文件类型，用类 HTML 语法描述一个 Vue 组件。每个 `.vue` 文件包含三种类型的顶级语言块 `<template>`、`<script>` 和 `<style>`，还允许添加可选的自定义块
	- `vue-loader` 会解析文件，提取每个语言块，如有必要会通过其它 loader 处理，最后将他们组装成一个 ES Module，它的默认导出是一个 Vue.js 组件选项的对象。
