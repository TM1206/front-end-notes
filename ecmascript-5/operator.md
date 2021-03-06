JavaScript 提供了一组用于操作数据值的运算符。- 算数运算符（+  -  *  /  %  ++  --）
- 比较运算符（>  >=  <  <=  ==  !=  ===  !==）
- 逻辑运算符（&&  ||  !）
- 赋值运算符（=  +=  -=  *=  /=  %=  ）
- 字符串连接运算符（+）
- 三元运算符（? :）
- 特殊运算符（typeof  instanceof  delete）

## 算数运算符

给定 A=20 B=10 条件，下述表格描述算数运算符:

| 运算符 | 描述 | 例子 |
| --- | --- | --- |
| + | 两个运算数相加 | A + B = 30 |
| - | 第一个运算数减去第二个运算数 | A – B = 10 |
| * | 两个运算数相乘 | A * B = 200 |
| / | 第一个运算数除以第二个运算数 | A / B = 2 |
| % | 求余运算符，计算整除后的余数 | A % B = 0 |
| ++ | 增量运算符，整数值逐次加 1 | A++ = 21 |
| -- | 减量运算符，整数值逐次减 1 | A-- = 19 |

算数运算符的基本操作比较简单，但下述情况需要特别注意:

- 如果运算数中的一个或两个是字符串类型，JavaScript 会自动转换为数字值，再进行计算。
- 如果运算数中的一个或两个是字符串类型，但其中的字符不是数字，JavaScript 会自动转换数字值失败，得到 NaN 结果。
- 任何一个运算数是 NaN，结果都是 NaN。
- 布尔值 false 和 true 会转换为 0 和 1 进行计算。

### 求余运算符

求余运算符，用于计算两个运算数整除后的余数。```javascript
console.log( 10 % 3 );// 输出 1console.log( -10 % 3 );// 输出 -1console.log( 10 % -3 );// 输出 1console.log( -10 % -3 );// 输出 -1
```

### 自增运算符

自增运算符，用于整数值逐次加 1。分别具有两种用法:

- 前置型：自增运算符位于运算数之前。先加 1，再赋值。
- 后置型：自增运算符位于运算数之后。先赋值，再加 1。

```javascript
var x = 3;console.log( x++ );// 输出 3console.log( x );// 输出 4var y = 3;console.log( ++y );// 输出 4console.log( y );// 输出 4
```

### 自减运算符

自减运算符，用于整数值逐次减 1。分别具有两种用法:

- 前置型：自增运算符位于运算数之前。先减 1，再赋值。
- 后置型：自增运算符位于运算数之后。先赋值，再减 1。

```javascript
var x = 3;console.log( x-- );// 输出 3console.log( x );// 输出 2var y = 3;console.log( --y );// 输出 2console.log( y );// 输出 2
```

## 比较运算符给定 A=20 B=10条件，下述表格描述比较运算符:

| 运算符 | 描述 | 例子 |
| --- | --- | --- |
| == | 检查两个运算数的值是否相等，如果相等则结果为 true | A == B 为 false |
| != | 检查两个运算数的值是否不等，如果不等则结果为 true | A != B 为 true |
| > | 检查左边运算数是否大于右边运算数，如果是则结果为 true | A > B 为 true |
| >= | 检查左边运算数是否大于或等于右边运算数，如果是则结果为 true | A >= B 为 true |
| < | 检查左边运算数是否小于右边运算数，如果是则结果为 true | A < B 为 false |
| <= | 检查左边运算数是否小于或等于右边运算数，如果是则结果为 true | A <= B 为 false |

### 全等与全不等| 运算符 | 描述 |
| --- | --- |
| === | 两个运算数的值相等并且类型相同时，结果为 true |
| !== | 两个运算数的值不等或者类型不同时，结果为 true |

```javascript
var x = 10;var y = '10';console.log( x == y );// 输出 trueconsole.log( x === y );// 输出 falseconsole.log( x != y );// 输出 falseconsole.log( x !== y );// 输出 true
```

### isNaN 函数

isNaN() 函数用于判断其参数是否为 NaN（非数字值）。多用于检测使用类型转换函数进行数据类型转换后的结果是否为合法的数字值。> **值得注意的是:** NaN 与任何值（包括自身）进行比较，结果都是 false。不能使用 `==` 或者 `===` 运算符判断某个值是否是 NaN，而只能使用isNaN() 函数。

```javascript
console.log(isNaN(parseInt('123.45a')));// 输出 trueconsole.log(isNaN('123.45a'));// 输出 trueconsole.log(isNaN(Number('123.45a')));// 输出 true
```

## 逻辑运算符给定 A=20 B=10条件，下述表格描述比较运算符:

| 运算符 | 描述 | 例子 |
| --- | --- | --- |
| `&&` | 逻辑与运算符。如果两个运算数都是 true，则返回 true | A && B 为 true |
| `||` | 逻辑或运算符。如果两个运算数中任何一个是 true，则返回 true | A || B 为 true |
| `!` | 逻辑非运算符。用于改变运算数的逻辑状态。如果逻辑状态为 true，则通过逻辑非运算符是逻辑状态改为 false | !(A && B) 为 false |

### 逻辑与运算符| B1 | B2 | B1 && B2 |
| --- | --- | --- |
| false | false | false |
| false | true | false |
| true | false | false |
| true | true | true |

```javascript
console.log( false && true );// 输出 falseconsole.log( true && true );// 输出 true// 数字值 1 和 0 转换为布尔值 true 和 falseconsole.log( 1 && 0 );// 输出 false// 空字符串转换为布尔值 false，非空字符串转换为布尔值 trueconsole.log( "" && "atguigu" );// 输出 false
```

### 逻辑或运算符| B1 | B2 | B1 或 B2 |
| --- | --- | --- |
| false | false | false |
| false | true | true |
| true | false | true |
| true | true | true |

```javascript
console.log( false || true );// 输出 trueconsole.log( false || false );// 输出 false// 数字值 1 和 0 转换为布尔值 true 和 falseconsole.log( 1 || 0 );// 输出 true// 空字符串转换为布尔值 false，非空字符串转换为布尔值 trueconsole.log( "" || "atguigu" );// 输出 true
```

### 逻辑非运算符

| B1 | !B1 |
| --- | --- |
| false | true |
| true | false |

```javascript
console.log( !true );// 输出 falseconsole.log( !1 );// 输出 falseconsole.log( !"atguigu" );// 输出 false
```

> **值得注意的是:** 能被转换为 false 的值有null, 0, NaN, 空字符串("") 和 undefined。

### 逻辑短路原则

所谓短路原则，就是只要确定运算符前面的运算数为 true 或 false，就可以确定返回结果为 true 或 false。

- 逻辑与运算符
	- 逻辑与运算符前面为false，结果都将返回逻辑与运算符前面的。
	- 逻辑与运算符前面为true，结果都将返回逻辑与运算符后面的值。
- 逻辑或运算符
	- 逻辑或运算符前面为false，结果都将返回逻辑或运算符后面的值。
	- 逻辑或运算符前面为true，结果都将返回逻辑或运算符前面的值。

## 赋值运算符赋值运算符用于为变量或属性进行赋值操作。```javascript
var atguigu = "atguigu";// 将字符串 "atguigu" 赋值给变量 atguiguvar obj.x = 1;// 将数字值 1 赋值给 obj 对象的 x 属性
```

赋值运算符就是将右边运算数的值赋给左边运算数。```javascript
C = A + B;// 将A+B的值赋给C
```

| 运算符 | 描述 | 例子 |
| --- | --- | --- |
| += | 加等赋值运算符，将右边运算符与左边运算符相加并将运算结果赋给左边运算数 | C += A 相当于 C = C + A |
| -= | 减等赋值运算符，将左边运算数减去右边运算数并将运算结果赋给左边运算数 | C -= A 相当于 C = C - A |
| *= | 乘等赋值运算符，将右边运算数乘以左边运算数并将运算结果赋给左边运算数 | C *= A 相当于 C = C * A | 
| /= | 除等赋值运算符， 将左边运算数除以右边运算数并将运算结果赋值给左边运算数 | C /= A 相当于 C = C / A |
| %= | 模等赋值运算符，用两个运算数做取模运算并将运算结果赋值给左边运算数 | C %= A 相当于 C = C % A |

> **值得注意的是:** C += A由于运行时可以进行优化，执行效率都要优于C = C + A。

### 字符串连接运算符字符串连接运算符使用的是加法运算符（+）。- 两个运算数都是数字值时，"+"用于两个运算数相加计算。
- 两个运算数中的一个是字符串时，"+"用于字符串连接计算。```javascript
var num1 = 1;var num2 = 2;var num3 = num1 + num2; // 加法计算var num4 = "4";var num5 = num1 + num4; //字符串拼接计算 
```

## 条件运算符条件运算符，首先判断一个表达式是真或假，然后根据判断结果执行两个给定指令中的一个。| 运算符 | 描述 | 说明 |
| --- | --- | --- |
| ? : | 条件表达式 | 如果条件为真 ? X值 : Y值 |

```javascript
var age = 20;var msg = age > 18 ? "成年人" : "未成年人";
```

### 条件运算符嵌套

条件运算符中，每个表达式可以又是一个条件运算表达式，称为条件运算的嵌套。```javascript
var score = 85;var result = score >= 80 ? "优秀" : (			score >= 60 ? "合格" ："不合格"		);
```

上述代码的执行顺序如下:

1. 执行 score >= 60 ? "合格" ："不合格" 条件运算符。
2. 根据上一行的计算结果，再执行 score >= 80 ? "优秀" : 条件运算符### 运算符的优先级

下面的表将所有运算符按照优先级的不同从高到低排列:

![](24.png)