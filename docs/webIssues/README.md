# 移动端常见问题 #
移动端开发常见问题汇总

## 目录
- [需要长按但不选中文本的方法](#需要长按但不选中文本的方法)
- [微信客户端二维码长按识别注意事项](#微信客户端二维码长按识别注意事项)
- [安卓输入框弹出键盘遮盖住文本框的解决办法](#安卓输入框弹出键盘遮盖住文本框的解决办法)

### 需要长按但不选中文本的方法

```css
//css
-webkit-touch-callout: none; /* disables the callout */
-webkit-user-select:none;
```

### 微信客户端二维码长按识别注意事项

```html
//html 用img标签
<img class="qr" src="img/s4/qr.png" alt="">
```

### 安卓输入框弹出键盘遮盖住文本框的解决办法

```javascript
if(/Android [4-6]/.test(navigator.appVersion)) {
	window.addEventListener("resize", function() {
		if(document.activeElement.tagName=="INPUT" || document.activeElement.tagName=="TEXTAREA") {
			window.setTimeout(function() {
				document.activeElement.scrollIntoViewIfNeeded();
			},0);
		}
	})
}
```
