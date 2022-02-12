# StringUtils
字符串相关工具类

---

## convertToStr()

将变量的值转换为对应的字符串形式

```
convertToStr(arg: any): string
```

**注意**

该方法只支持`number`、`string`、`boolean`、`null`、`undefined`、`Date`，`object`类型的参数转换成字符串形式；其它如`Array`和`Function`等类型的参数不做转换，原样返回。

示例
```
convertToStr(123);						// 返回'123'
convertToStr(new Number(456));			// 返回'456'
convertToStr('');						// 返回''
convertToStr(true);						// 返回'true'
convertToStr(null);						// 返回"null"
convertToStr(undefined);				// 返回'undefined'
convertToStr({name: 'test'});			// 返回'{"name":"test"}'
convertToStr([]);						// 返回[]
```

___

## strIsEqual()

两个参数经过 [convertToStr()](utils-docs/StringUtils?id=converttostr) 转换后，使用`===`判断是否相等。
```
strIsEqual(arg1: any, arg2: any): boolean
```

返回值

`boolean`，true / false

示例

```
strIsEqual(123, '123');				// true
strIsEqual(null, undefined);		// false
```



---
