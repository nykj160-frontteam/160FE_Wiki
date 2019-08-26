# vue开发规范

## 命名规范

### 变量命名规范

命名方法：<b>驼峰命名法</b>

```javascript
let myName = "我的名字";
let names = [];
```

### 常量命名规范

命名方法 : <b>全部大写</b>

```javascript
const MAX_COUNT = 10
const URL = 'https://www.baidu.com/'
```

### 组件命名规范

官方文档推荐及使用遵循规则

**PascalCase (单词首字母大写命名)是最通用的声明约定**

**kebab-case (短横线分隔命名) 是最通用的使用约定**


1、组件名应该始终是多个单词的，根组件 App 除外

2、有意义的名词、简短、具有可读性

3、命名遵循 PascalCase 约定

4、使用遵循 kebab-case 约定

5、页面内部组件以组件模块名简写为开头，Item 为结尾，如（SearchItem，SearchListItem）

6、在页面中使用组件需要前后闭合，并以短线分隔，如（```<search-item></search-item>，<search-list-item></search-list-item>```）

7、导入及注册组件时，遵循 PascalCase 约定

8、同时还需要注意：必须符合自定义元素规范: 切勿使用保留字。

### method 方法命名命名规范

驼峰式命名，统一使用动词或者动词+名词形式；
请求数据方法，以 data 结尾
```javascript
jumpPage、openCarInfoDialog
getListData、postFormData
```
尽量使用常用单词开头（set、get、go、can、has、is）

### props 命名

<b style="color:#f00">在声明 prop 的时候，其命名应该始终使用 camelCase，而在模板中应该始终使用 kebab-case</b>

```javascript
props: {
    bannerData: {
        type: Object,
        default: []
    }
},
<newTopBanner :banner-data="top_ad_list"></newTopBanner>
```


## 结构化规范

### vue 文件基本结构
```javascript
<!-- 公用组件：banner轮播
  /**
  * 组件名称
  * @module 组件存放位置
  * @desc 组件描述
  * @author 组件作者
  * @date 2019年7月31日10:50
  * @interface 接口地址
  * @document 接口文档
  * @example 调用示例
  * <newTopBanner :banner-data="top_ad_list" :noimg="noImg"></newTopBanner>
  */ -->
<template>
    <div>
        <!--必须在div中编写页面-->
    </div>
</template>
<script>
    export default {
		components: {

		},
		/**
         * bannerData 是轮播banner数据列表
         * noimg表示没有图片的默认图
         */
		props: {
			bannerData: {
				type: Object,
                default: []
			},
			noimg: {
				type: String,
				default: ''
			}
		},
		data() {
			return {

			}
		},
        computed: {

        },
        created() {

        },
		mounted() {

		},
		methods: {

		},
        filters: {

        }
	}
</script>
<!--声明语言，并且添加scoped-->
<style lang="scss" scoped>
</style>
```

### 组件选项顺序
```javascript
    - components
    - props
    - data
    - computed
    - created
    - mounted
    - methods
    - filters
    - watch
```

## 注释规范

代码注释在一个项目的后期维护中显的尤为重要，所以我们要为每一个被复用的组件编写组件使用说明，为组件中每一个方法编写方法说明


**注释必填列表**

★公共组件使用说明

★各组件中重要函数或者类说明

★复杂的业务逻辑处理说明

★特殊情况的代码处理说明,对于代码中特殊用途的变量、存在临界值、函数中使用的 hack、使用了某种算法或思路等需要进行注释描述

★多重 if 判断语句

★注释块必须以/**（至少两个星号）开头**/

★单行注释使用//

**单行注释**

单行属性，注释写在行尾。例如：

```javascript
var name = "fanfan";// 姓名
```

**多行注释**

多行属性，注释写在行上

```javascript
// 重置
reset(){
    this.params = {}
    this.page = 1
    this.per_page = 10
    this.search()
},
/**
 *@desc  改变状态
 *@param  id      [String]  改变对象的id
 *@param  status  [String]  改变对象的status
 *@return config  [Object]  配置对象
 */
changeStatus(id, status) {
  
}
```

**公共模板组件注释说明**

```javascript
<!-- 公用组件：banner轮播
  /**
  * 组件名称
  * @module 组件存放位置
  * @desc 组件描述
  * @author 组件作者
  * @date 2019年7月31日10:50
  * @interface 接口地址
  * @document 接口文档
  * @example 调用示例
  * <new-top-banner :banner-data="top_ad_list" :noimg="noImg"></new-top-banner>
  */ -->
```


## CSS 编写顺序

```javascript
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  display: block;
  float: right;
  width: 100px;
  height: 100px;

  border: 1px solid #e5e5e5;
  border-radius: 3px;
  line-height: 1.5;
  text-align: center;

  font: normal 13px "Helvetica Neue", sans-serif;
  color: #333;
  background-color: #f5f5f5;
  opacity: 1;
```