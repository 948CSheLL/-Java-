# 1、初识Java





# 2、熟悉Eclipse开发工具





# 3、Java语言基础





# 4、流程控制





# 5、字符串



## 5.1、String类



## 5.2、连接字符串



## 5.3、获取字符串信息



## 5.4、字符串操作

### 5.4.8、字符串分割

1. 哪些字符用作分割符需要转义？

   答：”|.+*^?[\\{()$”。

   代码1：将”.”作为分割符。

   ```java
   String str="192.168.0.1";
   String[] firstArray=str.split("\\.");
   System.out.println("str的原值为：[" + str + "]");
   System.out.println("全部分割的结果：");
   for(String a : firstArray) {
   	System.out.print("[" + a + "]");
   }
   ```

   输出1：

   ```txt
   str的原值为：[192.168.0.1]
   全部分割的结果：
   [192][168][0][1]
   ```

   总结1：

   - 使用”.”作为分割符，在split()方法中要使用”\\”进行转义，即str.split(“\\.”)。

   

   代码2：将”|”作为分割符。

   ```java
   String str="192|168|0|1";
   String[] firstArray=str.split("\\|");
   System.out.println("str的原值为：[" + str + "]");
   System.out.println("全部分割的结果：");
   for(String a : firstArray) {
   	System.out.print("[" + a + "]");
   }
   ```

   输出2：

   ```txt
   str的原值为：[192|168|0|1]
   全部分割的结果：
   [192][168][0][1]
   ```

   总结2：

   - 使用”.”作为分割符，在split()方法中要使用”\\”进行转义，即str.split(“\\|”)。
   - 对于以上转义字符，如果要用split()方法分割，写法为str.split(“\\转义字符”)。



## 5.5、格式化字符串

### 5.5.1、日期和时间字符串格式化

1. 常用的日期格式化转换符

   代码1：采用转化符“%te”

   ```java
   Date date=new Date();				   // 创建Date对象data
   String day=String.format("%te", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(day);
   ```

   输出1：

   ```txt
   Wed May 27 14:32:39 CST 2020
   27
   ```

   总结1：

   - “%te”可以输出Date对象data中“年月日”中的“日”。

   

   代码2：采用转化符“%tb”

   ```java
   Date date=new Date();					// 创建Date对象data
   String month=String.format("%tb", date);// 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(month);
   ```

   输出2：

   ```txt
   Wed May 27 14:45:27 CST 2020
   5月
   ```

   总结2：

   - “%tb”可以显示指定语言环境月份简称。

   

   代码3：采用转化符“%tB”

   ```java
   Date date=new Date();					// 创建Date对象data
   String month=String.format("%tB", date);  // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(month);
   ```

   输出3：

   ```txt
   Wed May 27 14:50:28 CST 2020
   五月
   ```

   总结3：

   - “%tB”可以显示指定语言环境月份全称。

   

   代码4：采用转化符“%tA”

   ```java
   Date date=new Date();					// 创建Date对象data
   String week=String.format("%tA", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(week);
   ```

   输出4：

   ```txt
   Wed May 27 14:52:46 CST 2020
   星期三
   ```

   总结4：

   - “%tA”可以显示指定语言环境星期几的全称。

   

   代码5：采用转化符“%ta”

   ```java
   Date date=new Date();					// 创建Date对象data
   String week=String.format("%ta", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(week);
   ```

   输出5：

   ```txt
   Wed May 27 14:55:03 CST 2020
   周三
   ```

   总结5：

   - “%ta”可以显示指定语言环境星期几的简称。

   

   代码6：采用转化符“%tc”

   ```java
   Date date=new Date();					// 创建Date对象data
   String anotherData=String.format("%tc", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(anotherData);
   ```

   输出6：

   ```txt
   Wed May 27 14:56:15 CST 2020
   周三 5月 27 14:56:15 CST 2020
   ```

   总结6：

   - “%tc”是另一种显示全部日期和时间信息的格式。

   

   代码7：采用转化符“%tY”

   ```java
   Date date=new Date();					// 创建Date对象data
   String year=String.format("%tY", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(year);
   ```

   输出7：

   ```txt
   Wed May 27 14:59:46 CST 2020
   2020
   ```

   总结7：

   - “%tY”可以显示“年月日”中的4位“年”。

   

   代码8：采用转化符“%tj”

   ```java
   Date date=new Date();					// 创建Date对象data
   String whichDay=String.format("%tj", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(whichDay);
   ```

   输出8：

   ```txt
   Wed May 27 15:03:11 CST 2020
   148
   ```

   总结8：

   - “%tj”可以显示一个Date对象date的日期是所属年的哪一天。

   

   代码9：采用转化符“%tm”

   ```java
   Date date=new Date();					// 创建Date对象data
   String month=String.format("%tm", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(month);
   ```

   输出9：

   ```txt
   Wed May 27 15:07:37 CST 2020
   05
   ```

   总结9：

   - “%tm”可以显示二位数字月份。

   

   代码10：采用转化符“%td”

   ```java
   Date date=new Date();					// 创建Date对象data
   String day=String.format("%td", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(day);
   ```

   输出10：

   ```txt
   Wed May 27 15:13:22 CST 2020
   27
   ```

   总结10：

   - “%td”和”%te”的区别是“%td”显示的是“年月日”中的二位数字“日”。

   

   代码11：采用转化符“%ty”

   ```java
   Date date=new Date();					// 创建Date对象data
   String year=String.format("%ty", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(year);
   ```

   输出11：

   ```txt
   Wed May 27 15:17:39 CST 2020
   20
   ```

   总结11：

   - “%ty”可以显示二位数字年份。

   

2. 时间格式化转换符

   代码1：采用转化符“%tH”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tH", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出1：

   ```txt
   Wed May 27 15:23:04 CST 2020
   15
   ```

   总结1：

   - “%tH”可以显示二位数字24时制的小时。

   

   代码2：采用转化符“%tI”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tI", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出2：

   ```txt
   Wed May 27 15:25:01 CST 2020
   03
   ```

   总结2：

   - “%tI”可以显示二位数字12时制的小时。

   

   代码3：采用转化符“%tk”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tk", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出3：

   ```txt
   Wed May 27 15:26:28 CST 2020
   15
   ```

   总结3：

   - “%tk”和“%tH”的区别就是5小时显示的是“5”而不是“05”。

   

   代码4：采用转化符“%tl”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tl", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出4：

   ```txt
   Wed May 27 15:29:28 CST 2020
   3
   ```

   总结4：

   - “%tl”与”%tI”的区别是5小时小时“5”而不是“05”。

   

   代码5：采用转化符“%tM”

   ```java
   Date date=new Date();					// 创建Date对象data
   String minute=String.format("%tM", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(minute);
   ```

   输出5：

   ```txt
   Wed May 27 15:33:47 CST 2020
   33
   ```

   总结5：

   - “%tM”可以显示二位数字分钟。

   

   代码6：采用转化符“%tS”

   ```java
   Date date=new Date();					// 创建Date对象data
   String second=String.format("%tS", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(second);
   ```

   输出6：

   ```txt
   Wed May 27 15:36:19 CST 2020
   19
   ```

   总结6：

   - “%tS”可以显示二位数字秒钟。

   

   代码7：采用转化符“%tL”

   ```java
   Date date=new Date();					// 创建Date对象data
   String milliSecond=String.format("%tL", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(milliSecond);
   ```

   输出7：

   ```txt
   Wed May 27 15:39:45 CST 2020
   892
   ```

   总结7：

   - “%tL”可以显示三位数字毫秒。

   

   代码8：采用转化符“%tN”

   ```java
   Date date=new Date();					// 创建Date对象data
   String microSecond=String.format("%tN", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(microSecond);
   ```

   输出8：

   ```txt
   Wed May 27 15:50:53 CST 2020
   456000000
   ```

   总结8：

   - “%tN”可以显示9位微秒。

   

   代码9：采用转化符“%tp”

   ```java
   Date date=new Date();					// 创建Date对象data
   String morningOrAfternoon=String.format("%tp", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(morningOrAfternoon);
   ```

   输出9：

   ```txt
   Wed May 27 15:52:11 CST 2020
   下午
   ```

   总结9：

   - “%tp”可以显示指定语言环境的上下午。

   

   代码10：采用转化符“%tz”

   ```java
   Date date=new Date();					// 创建Date对象data
   String timeZoneOffset=String.format("%tz", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(timeZoneOffset);
   ```

   输出10：

   ```txt
   Wed May 27 15:54:28 CST 2020
   +0800
   ```

   总结10：

   - “%tz”可以显示相对于GMTRFC82格式的数字时区偏移量。

   

   代码11：采用转化符“%tZ”

   ```java
   Date date=new Date();					// 创建Date对象data
   String timeZone=String.format("%tZ", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(timeZone);
   ```

   输出11：

   ```txt
   Wed May 27 15:57:50 CST 2020
   CST
   ```

   总结11：

   - “%tZ”可以显示时区缩写的字符串。

   

   代码12：采用转化符“%ts”

   ```java
   Date date=new Date();					// 创建Date对象data
   String passedSecond=String.format("%ts", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(passedSecond);
   ```

   输出12：

   ```txt
   Wed May 27 15:59:32 CST 2020
   1590566372
   ```

   总结12：

   - “%ts”可以显示从1970-01-01 00:00:00至现在经过的秒数。

   

   代码13：采用转化符“%tQ”

   ```java
   Date date=new Date();					// 创建Date对象data
   String passedMillisecond=String.format("%tQ", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(passedMillisecond);
   ```

   输出13：

   ```txt
   Wed May 27 16:02:14 CST 2020
   1590566534984
   ```

   总结13：

   - “%tQ”可以显示从1970-01-01 00:00:00至现在经过的毫秒数。

   

3. 常见的日期和时间组合的格式

   代码1：采用转化符“%tF”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tF", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出1：

   ```txt
   Wed May 27 16:10:10 CST 2020
   2020-05-27
   ```

   总结1：

   - “%tF”显示的格式形如0000-00-00。

   

   代码2：采用转化符“%tD”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tD", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出2：

   ```txt
   Wed May 27 16:12:07 CST 2020
   05/27/20
   ```

   总结2：

   - “%tD”显示的格式形如00/00/00。

   

   代码3：采用转化符“%tc”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tc", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出3：

   ```txt
   Wed May 27 16:14:47 CST 2020
   周三 5月 27 16:14:47 CST 2020
   ```

   总结3：

   - “%tc”显示的格式如上。

   

   代码4：采用转化符“%tr”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tr", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出4：

   ```txt
   Wed May 27 16:16:29 CST 2020
   04:16:29 下午
   ```

   总结4：

   - “%tr”可以显示“时分秒”和上下午。

   

   代码5：采用转化符“%tT”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tT", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出5：

   ```txt
   Wed May 27 16:17:31 CST 2020
   16:17:31
   ```

   总结5：

   - “%tT”可以显示“时分秒”。

   

   代码6：采用转化符“%tR”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tR", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出6：

   ```txt
   Wed May 27 16:18:36 CST 2020
   16:18
   ```

   总结6：

   - “%tR”可以显示时分。

   

### 5.5.2、常规类型格式化

1. 常规转换符

   代码1：采用转换符”%b”或”%B”

   ```java
   // 测试3>5转化成boolean格式的字符串
   String boolTest=String.format("%b", 3>5);
   System.out.println(3>5);
   System.out.println("测试3>5转化成boolean格式的字符串:" + boolTest);
   // 测试3转化成boolean格式的字符串
   String boolTest1=String.format("%b", 3);
   System.out.println(3);
   System.out.println("测试3转化成boolean格式的字符串:" + boolTest1);
   // 测试0转化成boolean格式的字符串
   String boolTest2=String.format("%b", (int)0);
   System.out.println(0);
   System.out.println("测试0转化成boolean格式的字符串:" + boolTest2);
   // 测试-1转化成boolean格式的字符串
   String boolTest3=String.format("%b", -1);
   System.out.println(-1);
   System.out.println("测试-1转化成boolean格式的字符串:" + boolTest3);
   // 测试null转化成boolean格式的字符串
   String boolTest4=String.format("%b", null);
   System.out.println("null");
   System.out.println("测试null转化成boolean格式的字符串:" + boolTest4);
   ```

   输出1：

   ```txt
   false
   测试3>5转化成boolean格式的字符串:false
   3
   测试3转化成boolean格式的字符串:true
   0
   测试0转化成boolean格式的字符串:true
   -1
   测试-1转化成boolean格式的字符串:true
   null
   测试null转化成boolean格式的字符串:false
   ```

   总结1：

   - ”%b”或”%B”可以将3>5这个Boolean类型的变量转化成boolean格式的字符串。

   

   代码2：采用转化符”%h”或”%H”

   ```java
   // 测试long类型变量num的散列码
   long num=32123133132132123L;
   String longTest=String.format("%h", num);
   System.out.println("测试long类型变量num的散列码:" + longTest);
   ```

   输出2：

   ```txt
   测试long类型变量num的散列码:c31bd0ca
   ```

   总结2：

   - ”%h”或”%H”可以获取一个变量的散列码。可以用HashMap利用散列码和该变量值形成一个键值对，做到对该变量的快速查询。

   - 散列码就是通过一种不可逆的散列(hash)算法，对一个数据进行计算，获得一个“唯一”的值。这个值可以对这个数据进行标识，在查找数据的时候，可以通过这个值来快速定位数据，从而有效减少开销。	
   - 由于散列长度是有限和固定的，因抄此在数据极多的情况下散列值会出现重复，用术语讲就是“碰撞”。这个时候就需要其它方法来消除这种碰撞，比如再散列、拉链算法等。

   

   代码3：采用转化符”%s”或”%S”

   ```java
   // 测试long类型变量num转换成字符串
   long num=23423432423423423L;
   String longTest=String.format("%s", num);
   System.out.println("测试long类型变量num转换成字符串:" + longTest);
   ```

   输出3：

   ```txt
   测试long类型变量num转换成字符串:23423432423423423
   ```

   总结3：

   - ”%s”或”%S”可以将一个变量变成字符串。比较接近C++的语法。

   

   代码4：采用转化符”%c”或”%C”

   ```java
   // 测试int类型变量num转换成对应字符
   int num=83;
   String intTest=String.format("%c", num);
   System.out.println("测试int类型变量num转换成对应字符:" + intTest);
   ```

   输出4：

   ```txt
   测试int类型变量num转换成对应字符:S
   ```

   总结4：

   - 如果第二个参数是int类型，使用转换符”%c”或”%C”，会按照ascii码进行转化。

   

   代码5：采用转化符”%d”

   ```java
   // 测试int类型变量num转换成对应十进制的字符串
   int num=01232;                                  // 一个八进制数
   String intTest=String.format("%d", num);
   System.out.println("测试int类型变量num转换成对应十进制的字符串:" + intTest);
   ```

   输出5：

   ```txt
   测试int类型变量num转换成对应十进制的字符串:666
   ```

   总结5：

   - ”%d”可以将非十进制整数转换成符合十进制规则的字符串输出。

   

   代码6：采用转化符”%o”

   ```java
   // 测试int类型变量num转换成对应八进制的字符串
   int num=333; // 一个十进制数
   String intTest=String.format("%o", num);
   System.out.println("测试int类型变量num转换成对应八进制的字符串:" + intTest);
   ```

   输出6：

   ```txt
   测试int类型变量num转换成对应八进制的字符串:515
   ```

   总结6：

   - ”%o”可以将非八进制整数转换成符合八进制规则的字符串输出。

   

   代码7：采用转化符”%x”或”%X”

   ```java
   // 测试int类型变量num转换成对应十六进制的字符串
   int num=333; // 一个十进制数	
   String intTest=String.format("%x", num);
   System.out.println("测试int类型变量num转换成对应十六进制的字符串:" + intTest);
   ```

   输出7：

   ```txt
   测试int类型变量num转换成对应十六进制的字符串:14d
   ```

   总结7：

   - ”%x”可以将非八进制整数转换成符合十六进制规则的字符串输出。

   

   代码8：采用转化符”%e”

   ```java
   // 测试float类型变量num转换成对应计算机科学计数法表示的十进制的字符串
   float num=1000000.00f; // 一个十进制数
   String floatTest=String.format("%e", num);
   System.out.println("测试floatTest类型变量num转换成对应计算机科学计数法表示的十进制的字符串:" + floatTest);
   ```

   输出8：

   ```txt
   测试int类型变量num转换成对应计算机科学计数法表示的十进制的字符串:1.000000e+06
   ```

   总结8：

   - ”%e”可以将一个float类型转换成符合计算机科学计数法的十进制的字符串输出。

   

   代码9：采用转化符”%a”

   ```java
   // 测试float类型变量num转换成对应带有效位数和指数的十六进制浮点数的字符串
   float num=1000000.00f; // 一个十进制数
   String floatTest=String.format("%a", num);
   System.out.println("测试float类型变量num转换成对应带有效位数和指数的十六进制浮点数的字符串:" + floatTest);
   ```

   输出9：

   ```txt
   测试float类型变量num转换成对应带有效位数和指数的十六进制浮点数的字符串:0x1.e848p19
   ```

   总结9：

   - ”%a”可以将一个float类型转换成对应带有效位数和指数的十六进制浮点数的字符串。



## 5.6、使用正则表达式



## 5.7、字符串生成器

1. StringBuffer和StringBuilder的区别

   StringBuffer 和 StringBuilder 它们都是可变的字符串，而String类型是不可变的字符串，只能对字符常量进行操作，虽然可以通过“+”运算符进行字符串的拼接，但是每次拼接都会在内存创建一个新的字符对象，然后修改原String对象的索引，如果拼接的次数多了，会造成内存的负担。
   
   - 区别1：线程安全
   
     StringBuffer：线程安全，StringBuilder：线程不安全。因为 StringBuffer 的所有公开方法都是 synchronized 修饰的，而 StringBuilder 并没有 synchronized 修饰。
   
     StringBuffer 代码片段：
   
     ```java
     @Override
     public synchronized StringBuffer append(String str) {
         toStringCache = null;
         super.append(str);
         return this;
     }
     ```
   
     因此StringBuffer相比于StringBuilder在节约内存的同时，还保证了线程安全。详细的关于StringBuffer和StringBuilder的说明参见Java API。
   
     代码1：StringBuffer的创建与使用append方法进行字符串附加
   
     ```java
     // 创建一个新的StringBuffer对象并赋初值
     StringBuffer sbf=new StringBuffer("门前大桥下，");
     // 调用append方法进行字符串的修改，传入的参数可以是一个字符串
     sbf.append("游过一群鸭，");
     // 创建一个新的StringBuffer对象并赋初值
     StringBuffer tmp=new StringBuffer("快来快来数一数，");
     // 调用append方法进行字符串的修改，传入的参数可以是一个字符串生成器
     sbf.append(tmp);
     int x=24678;
     // 调用append方法进行字符串的修改，传入的参数可以是一个整数
     sbf.append(x);
     System.out.println(sbf.toString());
     ```
   
     输出1：
   
     ```txt
     门前大桥下，游过一群鸭，快来快来数一数，24678
     ```
   
     总结1：
   
     - XXX
   
     代码2：StringBuffer的创建与使用setCharAt方法修改字符串的某个位置的字符
   
     ```java
     StringBuffer sbf = new StringBuffer("0123456");
     sbf.setCharAt(3, 'A');
     System.out.println(sbf);
     ```
   
     输出2：
   
     ```txt
     012A456
     ```
   
     总结2：
   
     - XXX
   
     代码3：使用insert方法将某个字符串的到字符串生成器的某个位置
   
     ```java
     StringBuffer sbf=new StringBuffer("0123456");
     sbf.insert(5, "F");
     System.out.println(sbf);
     ```
   
     输出3：
   
     ```txt
     01234F56
     ```
   
     总结3：
   
     - XXX
   
     代码4：使用delete方法将删除子字符串
   
     ```java
     StringBuffer sbf=new StringBuffer("天行健，君子以自强不息");
     sbf=sbf.delete(4, 7);
     System.out.println(sbf);
     ```
   
     输出4：
   
     ```txt
     天行健，自强不息
     ```
   
     总结4：
   
     - XXX
   
     StringBuilder几乎和StringBuffer一样，只是单线程运行效率更高。
   
     以下是StringBuffer，StringBuilder和String的不同之处：
   
     ![img](file:///C:\Users\24189\AppData\Roaming\Tencent\Users\2418942810\TIM\WinTemp\RichOle\(AT[XJ{O[BV9CRV8]Y~)1@O.png)
   
     
   
     ![img](file:///C:\Users\24189\AppData\Roaming\Tencent\Users\2418942810\TIM\WinTemp\RichOle\%7@]_125R_93`LJ557`GV`S.png)
   
     
   
     ![img](file:///C:\Users\24189\AppData\Roaming\Tencent\Users\2418942810\TIM\WinTemp\RichOle\RRY[}SMHW93N$W94BPCVWCL.png)
   
   
   
   - 区别2：缓冲区
   
     StringBuffer 代码片段：
   
     ```java
     private transient char[] toStringCache;
     
     @Override
     public synchronized String toString() {
         if (toStringCache == null) {
             toStringCache = Arrays.copyOfRange(value, 0, count);
         }
         return new String(toStringCache, true);
     }
     ```
   
     StringBuilder 代码片段：
   
     ```java
     @Override
     public String toString() {
         // Create a copy, don't share the array
         return new String(value, 0, count);
     }
     ```
   
     可以看出，StringBuffer 每次获取 toString 都会直接使用缓存区的 toStringCache 值来构造一个字符串。
   
     而 StringBuilder 则每次都需要复制一次字符数组，再构造一个字符串。
   
     所以，缓冲区是对 StringBuffer 的一个优化吧，不过 StringBuffer 的这个toString 方法仍然是同步的。
   
   - 区别3：性能
   
     既然 StringBuffer 是线程安全的，它的所有公开方法都是同步的，StringBuilder 是没有对方法加锁同步的，所以毫无疑问，StringBuilder 的性能要远大于 StringBuffer。
     
   - 总结：
   
     所以，StringBuffer 适用于用在多线程操作同一个 StringBuffer 的场景，如果是单线程场合StringBuilder 更适合。

