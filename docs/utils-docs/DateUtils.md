
# DateUtils

日期相关工具类

---

## isDate()

校验参数是否为Date类型
```
isDate(arg: any): boolean
```

返回值
`boolean`，true / false

___


## getDateOfInterval()

获取基础日期的间隔日期

```
getDateOfInterval(interval: number, baseDate?: Date): Date
```

参数

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `interval` | `number` |  | 必填，如果为负数则返回基础日期之前的日期 |
| `baseDate` | ``null`` \| `Date` | `null` | 可选，基础日期，如果不传或者传`null`，则默认基础日期为今天 |

返回值

`Date`，新的`Date`对象

示例

```
const date = new Date(2022, 1, 11);			// 基础日期为2022年2月11日
getDateOfInterval(1, date);					// 返回间隔基础日期1天的日期，即2022年2月日
getDateOfInterval(-5, date);				// 返回间隔基础日期-5天的日期，即2022月2月6日
```



___

## getDatesFromDateRange()

获取时间范围内的日期，包含开始日期和结束日期
```
getDatesFromDateRange(startDate: Date, endDate: Date): Date[]
```
参数

| Name | Type | Description |
| :------ | :------ | :------ |
| `startDate` | `Date` | 开始日期，必填 |
| `endDate` | `Date` | 结束日期，必填 |

返回值

`Date[]`，日期数组

**注意**

开始日期和结束日期进行比较时是通过`getTime()`方法获取毫秒数进行比较大小。以开始日期为基础日期，循环加1天与结束日期进行比较。



___

## dateFormat()

日期格式化

```
dateFormat(date: Date, fmt?: string): string
```

参数

| Name | Type | Default value | Description |
| :------ | :------ | :------ | :------ |
| `date` | `Date` |  | 日期，必填 |
| `fmt` | `string` | `'YYYY-MM-dd'` | 格式，默认格式：YYYY-MM-dd，可选 |

**格式说明**

- y或者Y：年份，一般用yy表示两位年份，yyyy表示四位年份。
- M：一般用MM表示月份 (0 ~ 11)。
- d：一般用 dd 表示月份中的天数(1 ~ 31)。
- H或者h：一般用HH或者hh表示一天中的小时数 (0 ~ 23)。
- m：用mm表示分钟数 (0 ~ 59)。
- s：用ss表示秒数 (0 ~ 59)。

返回值

`string`，日期格式化后的`string`字符串

示例

```
const date = new Date();
date.setFullYear(2022, 1, 5);
dateFormat(date)                             // 返回 "2022-02-05"
dateFormat(date, 'YYYY-MM-dd hh:mm:ss')      // 返回 "2022-02-05 16:44:11"
```

___
