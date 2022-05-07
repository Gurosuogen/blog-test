## 渲染树
![css动画-渲染树.webp](https://raw.githubusercontent.com/Gurosuogen/blog-test/main/css%E5%8A%A8%E7%94%BB-%E6%B8%B2%E6%9F%93%E6%A0%91.webp)


浏览器渲染过程
1. DOM
2. CSSOM
3. 合并DOM 和 CSSOM 为 Render Tree（渲染树）
4. Layout（文档流、盒模型、计算大小和位置）
5. Paint （绘制边框颜色、文字颜色、阴影等）
6. Composite （根据层叠关系展示画面）

## 三种更新样式的方式
![css动画-三种更新方式.png](https://raw.githubusercontent.com/Gurosuogen/blog-test/main/css%E5%8A%A8%E7%94%BB-%E4%B8%89%E7%A7%8D%E6%9B%B4%E6%96%B0%E6%96%B9%E5%BC%8F.png)
1. JavaScript > Style > Layout > Paint > Composite
2. JavaScript > Style >  Paint > Composite
3. JavaScript > Style > Composite

不同属性更新样式的方式不同，可以通过[css triggers](https://csstriggers.com)进行查询。

## 优化
- JS优化 （使用requestAnimationFraame代替setTimeout或setInterval）
- CSS优化（使用will-change或translate）


## transform

### 常用功能
1. translate 位移
2. scale 缩放
3. rotate 旋转
4. skew 倾斜

## transition
- 补充中间帧
- display:none => block 无法过渡
- 改用 visibility:hidden => visible
- 没有中间点
	1. 使用多次transform
	2. js中监听transitionend或使用setTimeout

## animation
- 声明关键帧
- 添加动画
- [@keyframes 语法](https://developer.mozilla.org/zh-CN/docs/Web/CSS/@keyframes)
