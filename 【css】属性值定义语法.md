<!--
 * @Author: yangxin yangxin@weiling.cn
 * @Date: 2023-07-28 15:42:03
 * @LastEditors: yangxin yangxin@weiling.cn
 * @LastEditTime: 2023-08-07 11:38:39
 * @FilePath: \sliderbarc:\te\md\【css】层叠上下文.md
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
# 【css】属性值定义语法

css属性定义语法是专门用于限定css属性合法取值的语法，其包含3种基本组成元素：

- 关键字

- 数据类型

- 符号

## 分类

### 关键字

其分为通用关键字和全局关键字

- 通用关键字：
  
  `auto`, `none`, `ease`等是通用关键字，或者称为普通关键字，这些只能被一部分的css属性支持

- 全局关键字

  `inherit`, `initial`, `unset`和`revert`是全局关键字，被所有css属性支持的特殊关键字

### 数据类型

css的数据类型有很多，至少有50个，例如number、percent、rgb等，这些都是。以及还有`shape-box`，`basic-shape`，`image`也属于数据类型

- shape-box

  box、margin-box、content-box、padding-box、border-box都是属于其支持的属性值

- basic-shape

  inset()、circle()、ellipse()、polygon()、path()、clip-path和offset-path都属于

- image

  <url>，<gradient>，element()，image()，image-set()，cross-fade()，paint()

### 符号

css的符号分为字面符号、组合符号以及数量符号

#### 字面符号

指css属性种原本就支持的合法符号，这些符号会在css语法中按照其原本的字面意思呈现

| 符号 | 名称 | 描述 |
|-----|------| -----|
|, | 并列分隔符 | 用于分隔数个并列值，或者分隔函数的参数值 |
| / | 缩写分隔符 | 用于分隔一个值的多个部分，在css缩写中用于分离类型相同但属于不同css属性的值，以及用在部分css函数中 |

#### 组合符号

用于表示数个基本元素之间的组合关系

| 符号 | 名称 | 描述 |
|-----|------| -----|
|  | 并列 | 符号为空格字符，表示各部分必须出现，同时需要按照顺序出现 |
| && | 与 | 各部分必须出现，但可以不按顺序出现 |
| \|\| | 或 | 各部分至少出现一个，可以不按顺序出现 |
| \| | 互斥 | 各部分恰好出现其中一个 |
| [] | 方括号 | 将各部分进行分组以绕过上面几个符号的优先规则，其优先级最高|

#### 数量符号

用于描述一个元素可以出现次数，数量符号不能叠加，且优先级高于组合符号


| 符号 | 名称 | 描述 |
|-----|------| -----|
|  | 无数量符号 | 恰好出现一次 |
| * | 星号 | 可以出现任意次数 |
| + | 加号 | 可以出现一次或者多次 |
| ？ | 问号 | 可以出现零次或者一次 |
| {A, B} | 花括号 | 出现最少A次，最多B次 |
| # | 井号 | 可以出现一次或者多次，但多次出现时必须以逗号分隔 |
| ！ | 叹号 | 表示当前分组必须产生一个值，该符号多出现在组合符号方括号的后面 |