# NumberUtils

数字相关工具类，包括JS浮点数的四则运算方法，在一定程度上解决了JS浮点数运算时精度丢失的问题。

---

## Options

```typescript

class Options {
    /**
     * 参数是否需要进行转换，如果该属性值为true，则在后续检查中判断参数的布尔值是否为false，若为false，则将其转换为数字0
     */
    public transformFlag?: boolean = true;
}

```

## numberCheck()

`number`类型数字检查
```
numberCheck(arg: any[, options: Options]): any
```

1. 如果`options.transformFlag`值为`true`且参数值为`null`、`undefined`、`空字符串`时，则将参数值转换为数字`0`，否则不做转换；

2. 判断上一步处理后的参数值是否为正数、负数、小数，如果是则将参数原样返回，否则抛出`TypeError`。

返回值

`any`，number or error

___

## add()

两个数字相加求和

```
add(arg1: any, arg2: any, options?: Options): number
```

返回值

`number`，两数之和

___

## calcAdd()

多参数 加法运算

```
calcAdd(args: any[], options?: Options): number
```

返回值

`number`，所有参数的和

___

## calcDiv()

两数求商

```
calcDiv(arg1: any, arg2: any, options?: Options): number
```

返回值

`number`，两数的商

---


## calcMul()

两数求积

```
calcMul(arg1: number, arg2: number, options?: Options): number
```

返回值

`number`，两数乘积

___

## calcSub()

两个数字相减

语法

```
calcSub(arg1: number, arg2: number, options?: Options): number
```

返回值

`number`，两数差值

___
