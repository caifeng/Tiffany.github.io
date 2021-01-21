---
title: Input相关
date: 2021-01-21 14:14:19
tags:
---

### Chrome input自动填充背景去除
``` css
input:-webkit-autofill{
  transition: background-color 5000s ease-in-out 0s;
  text-fill-color:#303030;
  -webkit-text-fill-color:#303030;
}
```

### Input 自动填充密码和用户名

设置密码框和用户名框的name

### 去掉input 在iOS中的默认圆角和内阴影

``` css
input{
	-webkit-appearance: none;
	border-radius: 0;
}

```
###  焦点在 input 时，placeholder 没有隐藏

```css
input:focus::-webkit-input-placeholder{
	opacity: 0;
}

```

### input 输入框调出数字键盘

``` html
<!-- 数字键盘 带有符号，非九宫格样式 -->
<input type="number"/>

<!-- 九宫格数字键盘 -->
<input type="number" pattern="[0-9]*"/>

<!-- 电话号码键盘 -->
<input type="tel"/>

```


### 改变input placeholder颜色

```css

::-webkit-input-placeholder { /* WebKit browsers */
  color:    #999;
}
:-moz-placeholder { /* Mozilla Firefox 4 to 18 */
  color:    #999;
  opacity:  1;
}
::-moz-placeholder { /* Mozilla Firefox 19+ */
  color:    #999;
  opacity:  1;
}
:-ms-input-placeholder { /* Internet Explorer 10+ */
  color:    #999;
}

input::-webkit-input-placeholder, textarea::-webkit-input-placeholder { /* WebKit*/  
    color:    #666;  
}  
input:-moz-placeholder, textarea:-moz-placeholder { /* Mozilla Firefox 4 to 18 */  
    color:    #666;  
}  
input::-moz-placeholder, textarea::-moz-placeholder { /* Mozilla Firefox 19+ */  
    color:    #666;  
}  
input:-ms-input-placeholder, textarea:-ms-input-placeholder { /* IE 10+ */  
    color:    #666;  
} 

```
