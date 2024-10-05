# java string

构造函数

```java
String()
```

> 创建空字符串

```java
String(byte[] bytes)
```

> 通过字节数组来创建字符串，（默认解码器是根据java虚拟机的设置来的？utf-8？）

```java
String(byte[] bytes,Charset charset)
```

> 使用charset所指定的解码器来解析字节数组所对应的字符，并创建字符串

```java
String(byte[] bytes, int offset, int length)
```

> 用默认的解码器解析指定的   子！字节数组，生成对应的字符串

```java
String(byte[] bytes, int offset, int length, Charset charset)
```

> 用charset指定的解码器解析指定的   子！字节数组，生成对应的字符串

```java
String(byte[] bytes, int offset, int length, String charsetName)
```

> 用解析器名称（字符串，charsetname）指定的解析器解析指定的子字节数组，并生成新字符串

```java
String(byte[] bytes, String charsetName)
```

> 用解析器名称（字符串，charsetname）指定的解码器解析字节数组，并创建字符串

```java
String(char[] value)
```

> 用字符数组创建字符串

```java
String(char[] value, int offset, int count)
```

> 用字符数组的子数组创建字符串

```java
String(int[] codePoints, int offset, int count)
```

> 用unicode码点数组的子数组创建的字符串
>
> unicod码点：unicode中一个字符对应的唯一数字标识

```java
String(String original)
String(StringBuffer buffer)
String(StringBuilder builder)
```

> 对几种不同的字符串类型创建新的字符串对象（第一行，对自己也是，不过这叫复制）

> 总结
>
> string构造函数能传入字节数组，字符数组，整数数组和String，StringBuffer，StringBuilder类型
>
> offset		下标起始点
>
> count		元素个数
>
> 字节数组传参：
>
> Charset charset			表示一个解析器对象
>
> String charsetName	表示一个解析器名称



方法

```java
length()
```

> 返回类型：int
>
> 作用：返回字符串长度

```java
isEmpty()
```

> 返回类型：boolean
>
> 作用：判断字符串是否为空（length是否返回的是0），是->true

```java
charAt(int index)
```

> 返回类型：char
>
> 作用：返回指定索引对应的值
>
> 参数：
>
> index	索引
>
> error：如果参数小于0或大于字符串长度，抛出IndexOutOfBoundsException

```java
codePointAt(int index)
```

> 返回类型：int
>
> 作用：返回指定索引对应的unicode码点
>
> 参数：
>
> index	索引
>
> error：如果参数小于0或大于字符串长度，抛出IndexOutOfBoundsException

```java
codePointBefore(int index)
```

> 返回类型int
>
> 作用：返回索引前面的字符对应的unicode码点
>
> 参数：
>
> index	索引
>
> error：如果参数小于0或大于字符串长度，抛出IndexOutOfBoundsException
>
> 注意：我们所敲打出的字符数并不一定代表在计算机中存放时的字符数，有些字符是由两个字符构成的，也就是对一个字符使用length会返回2，所以当参数是2的时候可能返回的还是第一个元素

```java
codePointCount(int beginIndex,int endIndex)
```

> 返回类型int
>
> 作用：返回指定子字符串中的码点数（你输入的时候输入了几个字符，而非计算机里的）
>
> 参数
>
> beginIndex	起始索引（包括）
>
> endIndex		结束索引（不包括）
>
> error：如果参数小于0或大于字符串长度，抛出IndexOutOfBoundsException
>
> 增强版length

```java
offsetByCodePoints(int index,int codePointOffset)
```

> 返回类型int
>
> 作用：在指定索引的基础上偏移指定数量的码点，然后返回此时位置的索引
>
> 参数：
>
> index 	当前索引位置
>
> codePointOffset	偏移码点数
>
> error：如果参数小于0或大于字符串长度，抛出IndexOutOfBoundsException
>
> ​			codePointOffset为正数，从index开始的子字符串码点数小于他的情况下也会抛出上面的异常
>
> ​			负数也类似

```java
getChars(int srcBegin,int srcEnd,char[] dst,int dstBegin)
```

> 无返回类型
>
> 作用：将字符串的一部分复制到另一个字符串中
>
> 参数：
>
> srcBegin	起始索引
>
> srcEnd		结束索引
>
> dst			目的字符串
>
> dstBegin	在目的字符串中的起始位置
>
> error：起始索引为负数，起始索引大于结束索引，结束索引大于字符串长度，dstBegin为负数，
>
> dstBegin+(srcEnd-srcBegin)大于dst.length会抛出IndexOutOfBoundsException

```java
getBytes(String charsetName)
getBytes(Charset charset)
getBytes()
```

>返回类型byte[]
>
>作用：将字符串转换成字节码
>
>参数：
>
>charsetName 	字符集名称
>
>charset	字符集对象
>
>无参的那个是使用的默认字符集
>
>error：如果charsetName所表示的字符集并不支持，抛出UnsupportedEncodingException

```java
equals(Object anObject)
```

>返回类型boolean
>
>作用：比较两个对象的内容是否相等
>
>参数：
>
>anobject	表示另一个对象
>
>注意：不支持跨类比较内容，跨类比较的是地址是否相同

```java
contentEquals(StringBuffer sb)
contentEquals(CharSequence cs)
```

>返回类型boolean
>
>作用：比较和实现了Charsequence接口的对象，或是stringBuffer的对象的内容是否相等
>
>参数
>
>sb/cs	实现了charSequence接口的对象，stringbuffer也是实现了这个接口的对象

```java
equalsIgnoreCase(String anotherString)
```

>返回类型boolean
>
>作用：忽略大小写比较字符串内容是否相等
>
>参数
>
>anotherString	另一个字符串对象

```java
compareTo(String anotherString)
```

>返回类型int
>
>作用：对两个字符串按字母顺序挨个比较，大于的是正数，等于是0，小于是负数
>
>参数
>
>anotherString	另一个字符串对象

```java
compareToIgnoreCase(String str)
```

>返回类型int
>
>作用：忽略大小写，并对两个字符串按字母顺序挨个比较，大于的是正数，等于是0，小于是负数
>
>参数
>
>anotherString	另一个字符串对象



```java

```

>



扩展知识点：

unicode代理对

高代理（High Surrogate）：码点范围是 `U+D800` 到 `U+DBFF`。

低代理（Low Surrogate）：码点范围是 `U+DC00` 到 `U+DFFF`。

通过组合一个高代理和一个低代理，可以表示一个补充字符

假设我们要表示一个补充字符，例如笑脸表情符号 😊，它的 Unicode 码点是 U+1F60A。

高代理：
计算高代理：(0x1F60A - 0x10000) / 0x400 + 0xD800 = 0xD83D

低代理：
计算低代理：(0x1F60A - 0x10000) % 0x400 + 0xDC00 = 0xDE0A~~

补充字符：

范围：U+10000到U+10FFFF

代理对表示的字符所存放的位置

意思就是这里的能拆成两个代理对，也就是两个字符表示的一个字符，其他都是一个字符表示一个字符