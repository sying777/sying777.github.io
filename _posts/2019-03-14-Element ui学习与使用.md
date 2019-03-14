# Element ui学习与使用

## 安装

**npm**

基于nodejs环境

```java
npm i element-ui -S
```

**CDN**

```javascript
<!-- 引入样式 -->
<link rel="stylesheet" href="https://unpkg.com/element-ui/lib/theme-chalk/index.css">
<!-- 引入组件库 -->
<script src="https://unpkg.com/element-ui/lib/index.js"></script>
```



##上手

在main.js写入

```javascript
import Vue from 'vue';
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';
import App from './App.vue';

Vue.use(ElementUI);

new Vue({
  el: '#app',
  render: h => h(App)
});
```

## 表单验证

到官方文档复制粘贴

**注意点:**

* <el-form> 标签属性

  * :rules : 验证规则

  * :model :必须是对象,而<el-form-item>里的v-model为非对象

  * ref:相当于id的唯一标识的意思

    

* <el-form-item>标签属性
  * prop :这里的值必须和rules里的一致

    

## 遇坑点

### vue .native的使用

当你要在一个组件的根元素上绑定原生事件,那么就可以使用.native修饰符了,**会将子组件变成了普通的HTML标签，不加'. native'事件是无法触  发的。**

```html
<base-input v-on:focus.native="onFocus"></base-input>
```

