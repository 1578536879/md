# this

## 优先级
- 通过new进行创建的，this指向创建的对象

如果构造函数返回了一个对象，那么绑定的this就是返回对象的

如果构造函数没有返回对象，返回的是number或者boolean，那么实际返回的也是这个构造函数

- 显示绑定（bind/apply）：如果传的是null或者undefined，实际应用的是默认绑定规则
- 隐式绑定，绑定的是那个的上下文对象
``` is
Var fn(){}
Var obj = {fun: fun}
Obj.fun();//指向的是obj
```
- 默认绑定，严格模式下是undefined，非严格模式下是全局对象

## 实例

```
const a={ text:1,fn: function (){return this.text}}

const b={ text:1,fn: function (){
const aa=a.fn;
return aa();// 输出undefined，因为是在window层调用的
}}

```
