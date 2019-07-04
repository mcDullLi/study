## JS 数据类型

*20190704*


### 问题：请指出打印内容

```javascript
function changeObjProperty(o) {
  o.siteUrl = "http://www.baidu.com"
  o = new Object()
  o.siteUrl = "http://www.google.com"
} 
let webSite = new Object();
changeObjProperty(webSite);
console.log(webSite.siteUrl);
```







### 解析：

##### 数据类型：

- 基本数据类型
  - Null
  - Undefined
  - Boolean
  - Number
  - String
  - Symbol
  - Bigint
- 复杂数据类型： object等

##### 参数传递

基本类型是按照值来传递，复杂类型是按照引用传递

值传递：函数仅仅获取值。值得改变不影响传递过来的原始值

对象传递：函数内部修改会影响其原始值修改

**注意**：

```javascript
function changeStuff(state1, state2)
{
  state1.item = 'changed';
  console.log(state2) // {item: "unchanged"}
  state2 = {item: "changed"};
  console.log(state2) // {item: "changed"}
  /* 注意：{} 是字面量创建对象的一种方式。
  相当于
  state2 = new Object();
  state2.item = "changed";
  */
}
var obj1 = {item: "unchanged"};
var obj2 = {item: "unchanged"};
changeStuff(obj1, obj2);
console.log(obj1.item);  // 'changed'
console.log(obj2.item);  // 'unchanged'
```

#### 运行结果

所以运行结果是：http://www.baidu.com
