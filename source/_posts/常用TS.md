---
title: 常用TS
date: 2021-01-12 14:41:15
tags:
---

## 基础

### 只读 & 任意属性

```ts
interface Person {
    readonly id: number;
    name: string;
    age?: number;
    [key: string]: any;
}

```


### 可选参数

```ts
function buildName(firstName: string, lastName?: string) {
    if (lastName) {
        return firstName + ' ' + lastName;
    } else {
        return firstName;
    }
}

function buildName(firstName: string, lastName: string = 'Cat') {
    return firstName + ' ' + lastName;
}



```

可选参数必须接在必需参数后面。换句话说，可选参数后面不允许再出现必需参数了：

### 重载

```ts

function reverse(x: number): number;
function reverse(x: string): string;
function reverse(x: number | string): number | string {
    if (typeof x === 'number') {
        return Number(x.toString().split('').reverse().join(''));
    } else if (typeof x === 'string') {
        return x.split('').reverse().join('');
    }
}

```

### 断言

```ts

function getCacheData(key: string): any {
    return (window as any).cache[key];
}

interface Cat {
    name: string;
    run(): void;
}

const tom = getCacheData('tom') as Cat;
tom.run();


function getCacheData<T>(key: string): T {
    return (window as any).cache[key];
}

interface Cat {
    name: string;
    run(): void;
}

const tom = getCacheData<Cat>('tom');
tom.run();

```



### 枚举

枚举（Enum）类型用于取值被限定在一定范围内的场景，比如一周只能有七天，颜色限定为红绿蓝等。

```ts
enum Days {Sun, Mon, Tue, Wed, Thu, Fri, Sat};

```


### 类 与接口

```ts

interface Alarm {
    alert(): void;
}

interface Light {
    lightOn(): void;
    lightOff(): void;
}

class Car implements Alarm, Light {
    alert() {
        console.log('Car alert');
    }
    lightOn() {
        console.log('Car light on');
    }
    lightOff() {
        console.log('Car light off');
    }
}

```