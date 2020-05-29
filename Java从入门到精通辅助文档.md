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

   代码：将”.”作为分割符。

   ```java
   String str="192.168.0.1";
   String[] firstArray=str.split("\\.");
   System.out.println("str的原值为：[" + str + "]");
   System.out.println("全部分割的结果：");
   for(String a : firstArray) {
   	System.out.print("[" + a + "]");
   }
   ```

   输出：

   ```txt
   str的原值为：[192.168.0.1]
   全部分割的结果：
   [192][168][0][1]
   ```

   总结：

   - 使用”.”作为分割符，在split()方法中要使用”\\”进行转义，即str.split(“\\.”)。

   

   代码：将”|”作为分割符。

   ```java
   String str="192|168|0|1";
   String[] firstArray=str.split("\\|");
   System.out.println("str的原值为：[" + str + "]");
   System.out.println("全部分割的结果：");
   for(String a : firstArray) {
   	System.out.print("[" + a + "]");
   }
   ```

   输出：

   ```txt
   str的原值为：[192|168|0|1]
   全部分割的结果：
   [192][168][0][1]
   ```

   总结：

   - 使用”.”作为分割符，在split()方法中要使用”\\”进行转义，即str.split(“\\|”)。
   - 对于以上转义字符，如果要用split()方法分割，写法为str.split(“\\转义字符”)。



## 5.5、格式化字符串

### 5.5.1、日期和时间字符串格式化

1. 常用的日期格式化转换符

   代码：采用转化符“%te”

   ```java
   Date date=new Date();				   // 创建Date对象data
   String day=String.format("%te", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(day);
   ```

   输出：

   ```txt
   Wed May 27 14:32:39 CST 2020
   27
   ```

   总结：

   - “%te”可以输出Date对象data中“年月日”中的“日”。

   

   代码：采用转化符“%tb”

   ```java
   Date date=new Date();					// 创建Date对象data
   String month=String.format("%tb", date);// 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(month);
   ```

   输出：

   ```txt
   Wed May 27 14:45:27 CST 2020
   5月
   ```

   总结：

   - “%tb”可以显示指定语言环境月份简称。

   

   代码：采用转化符“%tB”

   ```java
   Date date=new Date();					// 创建Date对象data
   String month=String.format("%tB", date);  // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(month);
   ```

   输出：

   ```txt
   Wed May 27 14:50:28 CST 2020
   五月
   ```

   总结：

   - “%tB”可以显示指定语言环境月份全称。

   

   代码：采用转化符“%tA”

   ```java
   Date date=new Date();					// 创建Date对象data
   String week=String.format("%tA", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(week);
   ```

   输出：

   ```txt
   Wed May 27 14:52:46 CST 2020
   星期三
   ```

   总结：

   - “%tA”可以显示指定语言环境星期几的全称。

   

   代码：采用转化符“%ta”

   ```java
   Date date=new Date();					// 创建Date对象data
   String week=String.format("%ta", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(week);
   ```

   输出：

   ```txt
   Wed May 27 14:55:03 CST 2020
   周三
   ```

   总结：

   - “%ta”可以显示指定语言环境星期几的简称。

   

   代码：采用转化符“%tc”

   ```java
   Date date=new Date();					// 创建Date对象data
   String anotherData=String.format("%tc", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(anotherData);
   ```

   输出：

   ```txt
   Wed May 27 14:56:15 CST 2020
   周三 5月 27 14:56:15 CST 2020
   ```

   总结：

   - “%tc”是另一种显示全部日期和时间信息的格式。

   

   代码：采用转化符“%tY”

   ```java
   Date date=new Date();					// 创建Date对象data
   String year=String.format("%tY", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(year);
   ```

   输出：

   ```txt
   Wed May 27 14:59:46 CST 2020
   2020
   ```

   总结：

   - “%tY”可以显示“年月日”中的4位“年”。

   

   代码：采用转化符“%tj”

   ```java
   Date date=new Date();					// 创建Date对象data
   String whichDay=String.format("%tj", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(whichDay);
   ```

   输出：

   ```txt
   Wed May 27 15:03:11 CST 2020
   148
   ```

   总结：

   - “%tj”可以显示一个Date对象date的日期是所属年的哪一天。

   

   代码：采用转化符“%tm”

   ```java
   Date date=new Date();					// 创建Date对象data
   String month=String.format("%tm", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(month);
   ```

   输出：

   ```txt
   Wed May 27 15:07:37 CST 2020
   05
   ```

   总结：

   - “%tm”可以显示二位数字月份。

   

   代码：采用转化符“%td”

   ```java
   Date date=new Date();					// 创建Date对象data
   String day=String.format("%td", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(day);
   ```

   输出：

   ```txt
   Wed May 27 15:13:22 CST 2020
   27
   ```

   总结：

   - “%td”和”%te”的区别是“%td”显示的是“年月日”中的二位数字“日”。

   

   代码：采用转化符“%ty”

   ```java
   Date date=new Date();					// 创建Date对象data
   String year=String.format("%ty", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(year);
   ```

   输出：

   ```txt
   Wed May 27 15:17:39 CST 2020
   20
   ```

   总结：

   - “%ty”可以显示二位数字年份。

   

2. 时间格式化转换符

   代码：采用转化符“%tH”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tH", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出：

   ```txt
   Wed May 27 15:23:04 CST 2020
   15
   ```

   总结：

   - “%tH”可以显示二位数字24时制的小时。

   

   代码：采用转化符“%tI”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tI", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出：

   ```txt
   Wed May 27 15:25:01 CST 2020
   03
   ```

   总结：

   - “%tI”可以显示二位数字12时制的小时。

   

   代码：采用转化符“%tk”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tk", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出：

   ```txt
   Wed May 27 15:26:28 CST 2020
   15
   ```

   总结：

   - “%tk”和“%tH”的区别就是5小时显示的是“5”而不是“05”。

   

   代码：采用转化符“%tl”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tl", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出：

   ```txt
   Wed May 27 15:29:28 CST 2020
   3
   ```

   总结：

   - “%tl”与”%tI”的区别是5小时小时“5”而不是“05”。

   

   代码：采用转化符“%tM”

   ```java
   Date date=new Date();					// 创建Date对象data
   String minute=String.format("%tM", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(minute);
   ```

   输出：

   ```txt
   Wed May 27 15:33:47 CST 2020
   33
   ```

   总结：

   - “%tM”可以显示二位数字分钟。

   

   代码：采用转化符“%tS”

   ```java
   Date date=new Date();					// 创建Date对象data
   String second=String.format("%tS", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(second);
   ```

   输出：

   ```txt
   Wed May 27 15:36:19 CST 2020
   19
   ```

   总结：

   - “%tS”可以显示二位数字秒钟。

   

   代码：采用转化符“%tL”

   ```java
   Date date=new Date();					// 创建Date对象data
   String milliSecond=String.format("%tL", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(milliSecond);
   ```

   输出：

   ```txt
   Wed May 27 15:39:45 CST 2020
   892
   ```

   总结：

   - “%tL”可以显示三位数字毫秒。

   

   代码：采用转化符“%tN”

   ```java
   Date date=new Date();					// 创建Date对象data
   String microSecond=String.format("%tN", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(microSecond);
   ```

   输出：

   ```txt
   Wed May 27 15:50:53 CST 2020
   456000000
   ```

   总结：

   - “%tN”可以显示9位微秒。

   

   代码：采用转化符“%tp”

   ```java
   Date date=new Date();					// 创建Date对象data
   String morningOrAfternoon=String.format("%tp", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(morningOrAfternoon);
   ```

   输出：

   ```txt
   Wed May 27 15:52:11 CST 2020
   下午
   ```

   总结：

   - “%tp”可以显示指定语言环境的上下午。

   

   代码：采用转化符“%tz”

   ```java
   Date date=new Date();					// 创建Date对象data
   String timeZoneOffset=String.format("%tz", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(timeZoneOffset);
   ```

   输出：

   ```txt
   Wed May 27 15:54:28 CST 2020
   +0800
   ```

   总结：

   - “%tz”可以显示相对于GMTRFC82格式的数字时区偏移量。

   

   代码：采用转化符“%tZ”

   ```java
   Date date=new Date();					// 创建Date对象data
   String timeZone=String.format("%tZ", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(timeZone);
   ```

   输出：

   ```txt
   Wed May 27 15:57:50 CST 2020
   CST
   ```

   总结：

   - “%tZ”可以显示时区缩写的字符串。

   

   代码：采用转化符“%ts”

   ```java
   Date date=new Date();					// 创建Date对象data
   String passedSecond=String.format("%ts", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(passedSecond);
   ```

   输出：

   ```txt
   Wed May 27 15:59:32 CST 2020
   1590566372
   ```

   总结：

   - “%ts”可以显示从1970-01-01 00:00:00至现在经过的秒数。

   

   代码：采用转化符“%tQ”

   ```java
   Date date=new Date();					// 创建Date对象data
   String passedMillisecond=String.format("%tQ", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(passedMillisecond);
   ```

   输出：

   ```txt
   Wed May 27 16:02:14 CST 2020
   1590566534984
   ```

   总结：

   - “%tQ”可以显示从1970-01-01 00:00:00至现在经过的毫秒数。

   

3. 常见的日期和时间组合的格式

   代码：采用转化符“%tF”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tF", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出：

   ```txt
   Wed May 27 16:10:10 CST 2020
   2020-05-27
   ```

   总结：

   - “%tF”显示的格式形如0000-00-00。

   

   代码：采用转化符“%tD”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tD", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出：

   ```txt
   Wed May 27 16:12:07 CST 2020
   05/27/20
   ```

   总结：

   - “%tD”显示的格式形如00/00/00。

   

   代码：采用转化符“%tc”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tc", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出：

   ```txt
   Wed May 27 16:14:47 CST 2020
   周三 5月 27 16:14:47 CST 2020
   ```

   总结：

   - “%tc”显示的格式如上。

   

   代码：采用转化符“%tr”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tr", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出：

   ```txt
   Wed May 27 16:16:29 CST 2020
   04:16:29 下午
   ```

   总结：

   - “%tr”可以显示“时分秒”和上下午。

   

   代码：采用转化符“%tT”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tT", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出：

   ```txt
   Wed May 27 16:17:31 CST 2020
   16:17:31
   ```

   总结：

   - “%tT”可以显示“时分秒”。

   

   代码：采用转化符“%tR”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tR", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出：

   ```txt
   Wed May 27 16:18:36 CST 2020
   16:18
   ```

   总结：

   - “%tR”可以显示时分。

   

### 5.5.2、常规类型格式化

1. 常规转换符

   代码：采用转换符”%b”或”%B”

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

   输出：

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

   总结：

   - ”%b”或”%B”可以将3>5这个Boolean类型的变量转化成boolean格式的字符串。

   

   代码：采用转化符”%h”或”%H”

   ```java
   // 测试long类型变量num的散列码
   long num=32123133132132123L;
   String longTest=String.format("%h", num);
   System.out.println("测试long类型变量num的散列码:" + longTest);
   ```

   输出：

   ```txt
   测试long类型变量num的散列码:c31bd0ca
   ```

   总结：

   - ”%h”或”%H”可以获取一个变量的散列码。可以用HashMap利用散列码和该变量值形成一个键值对，做到对该变量的快速查询。

   - 散列码就是通过一种不可逆的散列(hash)算法，对一个数据进行计算，获得一个“唯一”的值。这个值可以对这个数据进行标识，在查找数据的时候，可以通过这个值来快速定位数据，从而有效减少开销。	
   - 由于散列长度是有限和固定的，因抄此在数据极多的情况下散列值会出现重复，用术语讲就是“碰撞”。这个时候就需要其它方法来消除这种碰撞，比如再散列、拉链算法等。

   

   代码：采用转化符”%s”或”%S”

   ```java
   // 测试long类型变量num转换成字符串
   long num=23423432423423423L;
   String longTest=String.format("%s", num);
   System.out.println("测试long类型变量num转换成字符串:" + longTest);
   ```

   输出：

   ```txt
   测试long类型变量num转换成字符串:23423432423423423
   ```

   总结：

   - ”%s”或”%S”可以将一个变量变成字符串。比较接近C++的语法。

   

   代码：采用转化符”%c”或”%C”

   ```java
   // 测试int类型变量num转换成对应字符
   int num=83;
   String intTest=String.format("%c", num);
   System.out.println("测试int类型变量num转换成对应字符:" + intTest);
   ```

   输出：

   ```txt
   测试int类型变量num转换成对应字符:S
   ```

   总结：

   - 如果第二个参数是int类型，使用转换符”%c”或”%C”，会按照ascii码进行转化。

   

   代码：采用转化符”%d”

   ```java
   // 测试int类型变量num转换成对应十进制的字符串
   int num=01232;                                  // 一个八进制数
   String intTest=String.format("%d", num);
   System.out.println("测试int类型变量num转换成对应十进制的字符串:" + intTest);
   ```

   输出：

   ```txt
   测试int类型变量num转换成对应十进制的字符串:666
   ```

   总结：

   - ”%d”可以将非十进制整数转换成符合十进制规则的字符串输出。

   

   代码：采用转化符”%o”

   ```java
   // 测试int类型变量num转换成对应八进制的字符串
   int num=333; // 一个十进制数
   String intTest=String.format("%o", num);
   System.out.println("测试int类型变量num转换成对应八进制的字符串:" + intTest);
   ```

   输出：

   ```txt
   测试int类型变量num转换成对应八进制的字符串:515
   ```

   总结：

   - ”%o”可以将非八进制整数转换成符合八进制规则的字符串输出。

   

   代码：采用转化符”%x”或”%X”

   ```java
   // 测试int类型变量num转换成对应十六进制的字符串
   int num=333; // 一个十进制数	
   String intTest=String.format("%x", num);
   System.out.println("测试int类型变量num转换成对应十六进制的字符串:" + intTest);
   ```

   输出：

   ```txt
   测试int类型变量num转换成对应十六进制的字符串:14d
   ```

   总结：

   - ”%x”可以将非八进制整数转换成符合十六进制规则的字符串输出。

   

   代码：采用转化符”%e”

   ```java
   // 测试float类型变量num转换成对应计算机科学计数法表示的十进制的字符串
   float num=1000000.00f; // 一个十进制数
   String floatTest=String.format("%e", num);
   System.out.println("测试floatTest类型变量num转换成对应计算机科学计数法表示的十进制的字符串:" + floatTest);
   ```

   输出：

   ```txt
   测试int类型变量num转换成对应计算机科学计数法表示的十进制的字符串:1.000000e+06
   ```

   总结：

   - ”%e”可以将一个float类型转换成符合计算机科学计数法的十进制的字符串输出。

   

   代码：采用转化符”%a”

   ```java
   // 测试float类型变量num转换成对应带有效位数和指数的十六进制浮点数的字符串
   float num=1000000.00f; // 一个十进制数
   String floatTest=String.format("%a", num);
   System.out.println("测试float类型变量num转换成对应带有效位数和指数的十六进制浮点数的字符串:" + floatTest);
   ```

   输出：

   ```txt
   测试float类型变量num转换成对应带有效位数和指数的十六进制浮点数的字符串:0x1.e848p19
   ```

   总结：

   - ”%a”可以将一个float类型转换成对应带有效位数和指数的十六进制浮点数的字符串。