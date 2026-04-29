---
title: 'TypeScript 高级技巧分享'
description: '探索 TypeScript 中的高级类型系统和实用技巧'
pubDate: 2024-02-20
heroImage: 'https://picsum.photos/seed/typescript/800/600'
tags: ['TypeScript', 'JavaScript', '类型系统']
categories: ['编程技巧']
draft: false
readingTime: 10
---

## 泛型的妙用

泛型是 TypeScript 中最强大的特性之一。让我们看一些实用的例子。

### 条件类型

```typescript
type IsString<T> = T extends string ? true : false;

type A = IsString<string>;  // true
type B = IsString<number>;  // false
```

### 映射类型

```typescript
type Readonly<T> = {
  readonly [P in keyof T]: T[P];
};

interface Person {
  name: string;
  age: number;
}

type ReadonlyPerson = Readonly<Person>;
```

## 工具类型

TypeScript 内置了很多实用的工具类型：

- `Partial<T>` - 将属性变为可选
- `Required<T>` - 将属性变为必填
- `Pick<T, K>` - 选择特定属性
- `Omit<T, K>` - 排除特定属性
- `Record<K, T>` - 创建记录类型

## 类型守卫

类型守卫可以帮助你在运行时缩小类型范围：

```typescript
function isString(value: unknown): value is string {
  return typeof value === 'string';
}

function print(value: string | number) {
  if (isString(value)) {
    console.log(value.toUpperCase());
  } else {
    console.log(value.toFixed(2));
  }
}
```

## 总结

掌握这些高级技巧可以让你的 TypeScript 代码更加类型安全和易于维护。
