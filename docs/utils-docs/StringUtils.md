# StringUtils
字符串相关工具类

## convertToStr()

将变量转换为string类型

```
convertToStr(arg: any): string
```

注意

该方法只支持`number`、`null`、`undefined`、`object`类型的参数转换成string字符串；`Array`和`Function`类型的参数不做转换，原样返回。

返回值

`string`

示例
```
convertToStr('');                 // 返回''
convertToStr(null);             // 返回"null"
convertToStr(undefined);       // 返回'undefined'
convertToStr({name: 'test'}); // 返回'{"name":"test"}'
convertToStr([]);           // 返回[]

```

___

## strIsEqual()

两个参数经过 [convertToStr()](#convertToStr()) 转换后，使用`===`判断是否相等。
```
strIsEqual(arg1: any, arg2: any): boolean
```

返回值

`boolean`，true/false

---
