# 元组

数组合并了相同类型的对象，而元组 Tuple 合并了不同类型的对象

元组起源于函数编程语言，这些语言会频繁使用元组

## 简单的例子

定义一对值分别为 string 和 number 的元组

```typescript
let tom: [string, number] = ['Tom', 25];
```

当赋值或访问一个已知索引的元素时，会得到正确的类型

```typescript
let tom: [string, number];
tom[0] = 'Tom';
tom[1] = 25;

tom[0].slice(1);
tom[1].toFixed(2);
```

当然也可以只赋值其中一项

```typescript
let tom: [string, number];
tom[0] = 'Tom';
```

但是当直接对元组类型的变量进行初始化或者赋值的时候，需要提供所有元组类型中指定的项

```typescript
let tom: [string, number];

tom = ['Tom', 25]; // true

tom = ['Tom']; //error
```

## 越界的元素

当添加越界的元素时，它的类型会被限制为元组中每个类型的联合类型

```typescript
let tom: [string, number];
tom = ['Tom', 25];
tom.push('male');
tom.push(true); // error 

// Argument of type 'true' is not assignable to parameter of type 'string | number'
```
