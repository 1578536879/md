## 类型

## 类型函数

### 过滤
- Exclude<T, U>

  从 T 中剔除可以赋值给 U 的类型。

- Extract<T, U>

  提取 T 中可以赋值给 U 的类型。

- Omit<T, U>

  构造一个除类型 U 中的属性外具有 T 属性的类型。

- NonNullable<T>

  从 T 中剔除 null 和 undefined。

- Record<K, T>

  构造一个具有类型 T 的一组属性 K 的类型

- Pick<T, K extends keyof T>

  从 T 中选择一组键位于并集 K 中的属性

### 描述

- Readonly<T>

  将 T 类型属性全部变为 readonly

- Partial<T>

  将 T 类型属性全部变为可选

- Required<T>

  将 T 类型属性全部变为必选

### 转换

- Uppercase<T extends string>

  将字符串文字类型转换为大写

- Lowercase<T extends string>

  将字符串文字类型转换为小写

- Capitalize<T extends string> / Uncapitalize<T extends string>

  将字符串文字类型的第一个字符转换为大/小写

### 函数相关

- Parameters<T extends (...args: any) => any>

  返回函数的参数

  ```ts
  function fn1(a: string, b = 2) {}
  type T1 = Parameters<typeof fn1>;
  // T1: [a: string, b?: number]
  ```

- ConstructorParameters<T extends abstract new (...args: any) => any>

  获取构造函数的参数

    ```ts
    class fn1 {
    constructor(a: number, b = 2) {}
    }

    type T1 = ConstructorParameters<typeof fn1>;
    // T1: [a: number, b?: number]
    ```

- ReturnType<T extends (...args: any) => any>

  获取函数返回参数

    ```ts
    function fn() {
    return {
        a: 1,
        b: 2,
    };
    }

    type T1 = ReturnType<typeof fn>;
    ```

- InstanceType<T extends abstract new (...args: any) => any>

  获取构造函数函数类型的返回类型
