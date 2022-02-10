# Utils

该文档中介绍的方法只支持通过方法名称调用。

## getVarType()

获取变量类型

```
getVarType(value: any): string
```

实现如下

```
Object.prototype.toString.call(value).slice(8, -1).toLowerCase()
```



## isNull()

检查`value`值是否为`null`

```
isNull(value: any): boolean
```



## isUndefined()

检查`value`值是否为`undefined`

```
isUndefined(value: any): boolean
```



## isNumber()

检查`value`的类型是否为`number`或者`Number`对象

```
isNumber(value: any): boolean
```



## isString()

检查`value`的类型是否为`string`或者`String`对象

```
isString(value: any): boolean
```



## isBoolean()

检查`value`的类型是否为`boolean`或者`Boolean`对象

```
isBoolean(value: any): boolean
```



## isSymbol()

检查`value`是否为`symbol`类型

```
isSymbol(value: any): boolean
```



## isObject()

检查`value`的类型是否为`Object`对象

```
isObject(value: any): boolean
```

在`value`不为`null`的情况下，使用`typeof`获取value的类型，如果类型为`object`或者`function`，则返回`true`，否则返回`false`



## isObj()

检查`value`类型是否为`object`对象

```
isObj(value: any): boolean
```

通过[`getVarType()`](utils-docs/Utils?id=getvartype)方法获取value的类型，如果是`object`，则返回`true`，否则返回`false`



## isArray()

检查`value`类型是否为`Array`对象

```
isArray(value: any): boolean
```



## isMap()

检查`value`值是否为`Map`类型

```
isMap(value: any): boolean
```



## isSet()

检查`value`值是否为`Set`类型

```
isSet(value: any): boolean
```



## isFunction()

检查`value`是否为`Function`

```
isFunction(value: any): boolean
```



## cloneDeep()

对`value`进行深拷贝(递归拷贝)

```
cloneDeep(value: any): any
```

1. 支持深拷贝的数据类型有`number`、`string`、`boolean`、`null`、`undefined`、`Number`、`String`、`Boolean`、`Map`、`Set`、`Object`、`Array`、`RegExp`、`Date`。
2. `Function`、`Int8Array`、`Uint8Array`、`Int16Array`等类型数据只会进行简单的复制，不会进行深拷贝。
