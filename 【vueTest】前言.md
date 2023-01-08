## 环境

- vue3

- node：v16.16.0

## 安装包

- jest：测试工具

- vue-jest：用于解析vue文件

- babel-jest：用于文件引入的加载

- ts-jest： ts解析

- @vue/babel-preset-jsx @vue/babel-helper-vue-jsx-merge-props  @babel/core @babel/preset-env  @vue/babel-preset-app:用于文件加载

- @vue/test-utils: 可以实现组件的挂载、与组件交互以及断言组件输出
## jest

``` json
"test": "jest --no-cache"
```


jest在查找项目的测试文件是使用默认的glob匹配模式，对于non-glob模式而会自动运行下面三个情况的文件：

- xxx.spec.js

- __test__文件夹下的js和jsx文件

- xxx.test.js


## 调试

- 在js文件中需要打断点的地方写上debugger

- 在命令行中加入：`"test:debugger": "node --inspect-brk ./node_modules/jest/bin/jest.js --no-cache --runInBand"`

- 运行此命令后，在chrome浏览器打开：`chrome://inspect`

- 可以看到有一个Remote Target部分中有node_modules/jest/bin/jest.js

- 单击`Inspect`可以打开Chrome Debugger窗口

## 报错

- Cannot destructure property 'config'

jest版本改为26

- babelJest.getCacheKey is not a function

 babel-jest版本需要和jest版本匹配，安装26的