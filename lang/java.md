# Java

## 数据类型

Java有两大类数据类型：
1. 基本数据类型（Primitive Data Types）

| 基本类型 | 大小  | 范围                              | 默认值   | 包装类    |
| -------- | ----- | --------------------------------- | -------- | --------- |
| byte     | 1字节 | -128 到 127                       | 0        | Byte      |
| short    | 2字节 | -32,768 到 32,767                 | 0        | Short     |
| int      | 4字节 | -2^31 到 2^31 - 1                 | 0        | Integer   |
| long     | 8字节 | -2^63 到 2^63 - 1                 | 0L       | Long      |
| float    | 4字节 | 约 ±3.40282347E+38F               | 0.0f     | Float     |
| double   | 8字节 | 约 ±1.79769313486231570E+308      | 0.0d     | Double    |
| boolean  | 1位   | true 或 false                     | false    | Boolean   |
| char     | 2字节 | '\u0000' (0) 到 '\uffff' (65,535) | '\u0000' | Character |

2. 引用数据类型（Reference Data Types）
   - 类
   - 接口
   - 数组


## 输入输出

### 标准输入输出概述

Java提供了三个标准流：
- System.out：标准输出流
- System.in：标准输入流
- System.err：标准错误输出流

### 格式化输出

使用 System.out.printf() 或 String.format()：
```java
System.out.printf("名字: %s, 年龄: %d%n", "Alice", 25);
String formatted = String.format("圆周率: %.2f", Math.PI);
System.out.println(formatted);
```

### 接收输入

常见使用方式：

```java
import java.util.Scanner;

Scanner scanner = new Scanner(System.in);

System.out.print("请输入您的名字: ");
String name = scanner.nextLine();

System.out.print("请输入您的年龄: ");
int age = scanner.nextInt();

System.out.println("您好，" + name + "！您今年" + age + "岁。");

scanner.close(); // 记得关闭 Scanner
```

Scanner 常用方法：

| 方法          | 描述                 |
| ------------- | -------------------- |
| nextLine()    | 读取一行文本         |
| next()        | 读取一个单词         |
| nextInt()     | 读取一个整数         |
| nextDouble()  | 读取一个双精度浮点数 |
| nextBoolean() | 读取一个布尔值       |

## 运算符

### 1. 算术运算符

| 运算符 | 描述 | 示例       |
| ------ | ---- | ---------- |
| +      | 加法 | a + b      |
| -      | 减法 | a - b      |
| *      | 乘法 | a * b      |
| /      | 除法 | a / b      |
| %      | 取余 | a % b      |
| ++     | 自增 | a++ 或 ++a |
| --     | 自减 | a-- 或 --a |

注：`++a`和`a++`的区别在于运算的时机。

### 2. 比较运算符

| 运算符 | 描述     | 示例   |
| ------ | -------- | ------ |
| ==     | 等于     | a == b |
| !=     | 不等于   | a != b |
| >      | 大于     | a > b  |
| <      | 小于     | a < b  |
| >=     | 大于等于 | a >= b |
| <=     | 小于等于 | a <= b |

### 3. 逻辑运算符

| 运算符 | 描述 | 示例     |
| ------ | ---- | -------- |
| &&     | 与   | a && b   |
| \|\|   | 或   | a \|\| b |
| !      | 非   | !a       |

### 4. 位运算符

| 运算符 | 描述       | 示例    |
| ------ | ---------- | ------- |
| &      | 按位与     | a & b   |
| \|     | 按位或     | a \| b  |
| ^      | 按位异或   | a ^ b   |
| ~      | 按位取反   | ~a      |
| <<     | 左移       | a << 2  |
| >>     | 右移       | a >> 2  |
| >>>    | 无符号右移 | a >>> 2 |

### 5. 赋值运算符

基本赋值运算符：`=`

复合赋值运算符：`+=`, `-=`, `*=`, `/=`, `%=`, `&=`, `|=`, `^=`, `<<=`, `>>=`, `>>>=`

### 6. 条件（三元）运算符

语法：`条件 ? 表达式1 : 表达式2`

示例：`int max = (a > b) ? a : b;`

### 7. instanceof 运算符

用于检查对象是否为特定类型的实例。

示例：`obj instanceof String`

### 8. 运算符优先级

优先级从高到低：
1. 后缀运算符：`()`, `[]`, `.`, `(params)`, `expr++`, `expr--`
2. 一元运算符：`++expr`, `--expr`, `+expr`, `-expr`, `~`, `!`
3. 乘法运算符：`*`, `/`, `%`
4. 加法运算符：`+`, `-`
5. 移位运算符：`<<`, `>>`, `>>>`
6. 关系运算符：`<`, `>`, `<=`, `>=`, `instanceof`
7. 相等运算符：`==`, `!=`
8. 按位与：`&`
9. 按位异或：`^`
10. 按位或：`|`
11. 逻辑与：`&&`
12. 逻辑或：`||`
13. 条件运算符：`?:`
14. 赋值运算符：`=`, `+=`, `-=`, 等

注：使用括号`()`可以改变运算顺序。

## 条件控制

### 选择结构

1. if 语句
   ```java
   if (条件) {
       // 代码块
   }
   ```

2. if-else 语句
   ```java
   if (条件) {
       // 条件为真时执行
   } else {
       // 条件为假时执行
   }
   ```

3. if-else if-else 语句
   ```java
   if (条件1) {
       // 条件1为真时执行
   } else if (条件2) {
       // 条件2为真时执行
   } else {
       // 所有条件为假时执行
   }
   ```

4. switch 语句
   ```java
   switch (表达式) {
       case 值1:
           // 代码块1
           break;
       case 值2:
           // 代码块2
           break;
       default:
           // 默认代码块
   }
   ```
   注：Java 12+ 支持 switch 表达式

5. 三元运算符
   ```java
   结果 = (条件) ? 值1 : 值2;
   ```

### 循环结构

1. for 循环
   ```java
   for (初始化; 条件; 更新) {
       // 循环体
   }
   ```

2. while 循环
   ```java
   while (条件) {
       // 循环体
   }
   ```

3. do-while 循环
   ```java
   do {
       // 循环体
   } while (条件);
   ```

4. for-each 循环 (增强for循环)
   ```java
   for (元素类型 变量 : 集合或数组) {
       // 循环体
   }
   ```

5. 循环控制
   - `break`: 跳出整个循环
   - `continue`: 跳过当前迭代，继续下一次迭代
   - 标签（label）: 用于控制嵌套循环

6. 无限循环
   ```java
   while (true) {
       // 循环体
   }
   ```
   或
   ```java
   for (;;) {
       // 循环体
   }
   ```

注意事项：
- 选择合适的控制结构以提高代码可读性和效率
- 避免死循环
- 嵌套层次不宜过多，影响可读性
- switch 语句中注意 break 的使用
- 循环中应有明确的终止条件

## 面向对象

- 内部类
- 抽象类
- 接口

## String

### 1. 创建字符串

```java
String s1 = "Hello";  // 字符串字面量
String s2 = new String("Hello");  // 使用构造函数
```

### 2. 字符串不可变性

String对象一旦创建，其值不能被改变。

### 3. 常用方法

- `length()`: 返回字符串长度
- `charAt(int index)`: 返回指定索引处的字符
- `substring(int beginIndex, int endIndex)`: 返回子字符串
- `toLowerCase()` / `toUpperCase()`: 转换大小写
- `trim()`: 去除首尾空白
- `equals(Object obj)`: 比较字符串内容
- `equalsIgnoreCase(String anotherString)`: 忽略大小写比较
- `startsWith(String prefix)` / `endsWith(String suffix)`: 检查前缀或后缀
- `indexOf(String str)` / `lastIndexOf(String str)`: 查找子串位置
- `replace(char oldChar, char newChar)`: 替换字符
- `split(String regex)`: 分割字符串

### 4. 字符串连接

```java
String s = "Hello" + " World";  // 使用 + 运算符
String s = String.join(" ", "Hello", "World");  // 使用 join 方法
```

### 5. 字符串比较

```java
s1.equals(s2);  // 比较内容
s1 == s2;  // 比较引用（不推荐用于比较字符串）
```

### 6. StringBuilder 和 StringBuffer

用于高效地处理可变字符串。

```java
StringBuilder sb = new StringBuilder();
sb.append("Hello").append(" World");
String result = sb.toString();
```

StringBuffer 是线程安全的版本。

### 7. 字符串格式化

```java
String.format("Name: %s, Age: %d", name, age);
```

### 8. 正则表达式

```java
String s = "Hello, World!";
boolean matches = s.matches("Hello.*");
```

### 9. 字符串池

Java维护一个字符串池，相同的字符串字面量会引用同一个对象。

### 10. 性能考虑

- 大量字符串操作时使用 StringBuilder
- 避免在循环中使用 "+" 连接字符串

### 11. Java 11+ 新特性

- `isBlank()`: 检查字符串是否为空或仅包含空白字符
- `strip()`, `stripLeading()`, `stripTrailing()`: 改进的去除空白方法
- `repeat(int count)`: 重复字符串
- `lines()`: 将字符串分割为行的流

## 数据结构和算法

| 类别         | 子类别     | 知识点                                                                                                                                                                                            |
| ------------ | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 基本数据结构 | 线性结构   | • 数组<br>• 链表<br>• 栈<br>• 队列                                                                                                                                                                |
|              | 树形结构   | • 二叉树<br>• 二叉搜索树<br>• 平衡树（AVL, 红黑树）<br>• 堆                                                                                                                                       |
|              | 图结构     | • 有向图<br>• 无向图                                                                                                                                                                              |
|              | 散列结构   | • 哈希表                                                                                                                                                                                          |
| 高级数据结构 |            | • Trie（字典树）<br>• 并查集<br>• 线段树<br>• 树状数组（Fenwick树）                                                                                                                               |
| 算法         | 排序       | • 冒泡排序 O(n²)<br>• 选择排序 O(n²)<br>• 插入排序 O(n²)<br>• 快速排序 O(n log n)<br>• 归并排序 O(n log n)<br>• 堆排序 O(n log n)<br>• 计数排序 O(n + k)<br>• 桶排序 O(n + k)<br>• 基数排序 O(nk) |
|              | 搜索       | • 线性搜索 O(n)<br>• 二分搜索 O(log n)<br>• 深度优先搜索（DFS）<br>• 广度优先搜索（BFS）                                                                                                          |
|              | 图算法     | • Dijkstra 最短路径<br>• Floyd-Warshall 算法<br>• Bellman-Ford 算法<br>• Kruskal 最小生成树<br>• Prim 最小生成树<br>• 拓扑排序                                                                    |
|              | 动态规划   | • 背包问题<br>• 最长公共子序列<br>• 最长递增子序列                                                                                                                                                |
|              | 贪心算法   | • 活动选择问题<br>• Huffman 编码                                                                                                                                                                  |
|              | 字符串算法 | • KMP 算法<br>• Rabin-Karp 算法<br>• 最长回文子串                                                                                                                                                 |
| Java集合框架 | List       | • ArrayList<br>• LinkedList<br>• Vector                                                                                                                                                           |
|              | Set        | • HashSet<br>• TreeSet<br>• LinkedHashSet                                                                                                                                                         |
|              | Queue      | • PriorityQueue<br>• ArrayDeque                                                                                                                                                                   |
|              | Map        | • HashMap<br>• TreeMap<br>• LinkedHashMap                                                                                                                                                         |
| 算法复杂度   | 时间复杂度 | O(1), O(log n), O(n), O(n log n), O(n²), O(2ⁿ)                                                                                                                                                    |
|              | 空间复杂度 | • 递归调用栈<br>• 辅助数据结构                                                                                                                                                                    |
| 高级主题     | 并发       | • ConcurrentHashMap<br>• BlockingQueue                                                                                                                                                            |
|              | 函数式编程 | • Stream API<br>• Lambda 表达式                                                                                                                                                                   |
|              | NP完全问题 | • 旅行商问题<br>• 图着色问题                                                                                                                                                                      |

## 泛型

### 类型参数吗命名约定

- E - Element
- K - Key
- N - Number
- T - Type
- V - Value

### 泛型类&方法&接口

```java
public class Box<T> {
    private T t;

    public void set(T t) { this.t = t; }
    public T get() { return t; }
}

// 使用
Box<Integer> integerBox = new Box<>();
integerBox.set(10);
```

```java
public <E> void printArray(E[] array) {
    for (E element : array) {
        System.out.print(element + " ");
    }
}

// 使用
Integer[] intArray = { 1, 2, 3 };
printArray(intArray);
```

```java
public interface Comparable<T> {
    int compareTo(T o);
}

// 实现
public class Person implements Comparable<Person> {
    public int compareTo(Person p) {
        // 比较逻辑
    }
}
```

## 类型匹配符

1. 无界通配符（Unbounded Wildcard）: `?`

   - 语法：`List<?>`
   - 用途：表示可以接受任何类型的列表。
   - 特点：
     - 只能从列表中读取元素，不能添加元素（除了null）。
     - 从列表中读取的元素类型为Object。
   - 示例：
     ```java
     public void printList(List<?> list) {
         for (Object item : list) {
             System.out.println(item);
         }
     }
     ```
   - 适用场景：当你只需要读取列表中的元素，而不关心具体类型时使用。

2. 上界通配符（Upper Bounded Wildcard）: `? extends T`

   - 语法：`List<? extends Number>`
   - 用途：表示可以接受T类型或T的任何子类型的列表。
   - 特点：
     - 可以从列表中读取元素，但不能添加元素（除了null）。
     - 从列表中读取的元素类型为T。
   - 示例：
     ```java
     public double sumOfList(List<? extends Number> list) {
         double sum = 0.0;
         for (Number num : list) {
             sum += num.doubleValue();
         }
         return sum;
     }
     ```
   - 适用场景：当你需要从列表中读取元素，并且知道它们都是某个特定类型的子类型时使用。

3. 下界通配符（Lower Bounded Wildcard）: `? super T`

   - 语法：`List<? super Integer>`
   - 用途：表示可以接受T类型或T的任何父类型的列表。
   - 特点：
     - 可以向列表中添加T类型或T的子类型的元素。
     - 从列表中读取的元素类型为Object。
   - 示例：
     ```java
     public void addNumbers(List<? super Integer> list) {
         for (int i = 1; i <= 10; i++) {
             list.add(i);
         }
     }
     ```
   - 适用场景：当你需要向列表中添加元素，并且知道列表的元素类型是某个特定类型的父类型时使用。

总结：
- 无界通配符（`?`）：最灵活，但功能最受限，主要用于读取操作。
- 上界通配符（`? extends T`）：允许读取操作，知道读出的元素至少是T类型。
- 下界通配符（`? super T`）：允许写入操作，可以添加T或T的子类型的元素。

## 异常处理

### 异常类层次结构

- `Throwable`
  - `Error`：严重问题，通常不处理
  - `Exception`
    - 检查型异常：编译时必须处理
    - 非检查型异常（`RuntimeException`）：运行时异常

### try-catch 语句

```java
try {
    // 可能抛出异常的代码
} catch (ExceptionType1 e1) {
    // 处理 ExceptionType1
} catch (ExceptionType2 e2) {
    // 处理 ExceptionType2
} catch (IOException | SQLException e) {
    // 处理多个异常
} finally {
    // 无论是否发生异常都会执行的代码
}
```

### thow 主动抛出异常

```java
public void readFile() throws IOException {
    // 方法体
    throw new IllegalArgumentException("无效参数");
}
```

### 自定义异常

```java
public class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}
```

### try-with-resources 语句

自动关闭实现 AutoCloseable 接口的资源:

```java
try (FileInputStream fis = new FileInputStream("file.txt")) {
    // 使用 fis
} catch (IOException e) {
    // 处理异常
}
```

## IO流

| 类型                                     | 用途               |
| ---------------------------------------- | ------------------ |
| **字节流**                               |                    |
| InputStream/OutputStream                 | 用于处理二进制数据 |
| FileInputStream/FileOutputStream         | 用于处理文件       |
| BufferedInputStream/BufferedOutputStream | 缓冲区进行读写的   |
| ObjectInputStream/ObjectOutputStream     | 对象的输入输出流   |
| **字符流**                               |                    |
| Reader/Writer                            | 处理文本           |
| FileReader/FileWriter                    | 处理文件           |
| BufferedReader/BufferedWriter            | 处理缓冲区         |
| StringReader/StringWriter                | 字符串处理         |

## 序列化与反序列化

- 序列化：将对象转换为字节流
- 反序列化：将字节流转换回对象

Why Serialize & Unserialize?  
- 持久化对象状态
- 网络传输对象
- 跨JVM传输对象

Basic usage

```java
// 序列化
ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("file.ser"));
out.writeObject(object);

// 反序列化
ObjectInputStream in = new ObjectInputStream(new FileInputStream("file.ser"));
MyClass object = (MyClass) in.readObject();

private void writeObject(ObjectOutputStream out) throws IOException {
    // 自定义序列化逻辑
}

private void readObject(ObjectInputStream in) throws IOException, ClassNotFoundException {
    // 自定义反序列化逻辑
}
```

## 反射

## 多线程

- 定义：线程是程序执行的最小单位
- 创建线程:
  1. 继承 Thread 类
  2. 实现 Runnable 接口（推荐）
- 线程控制:
  - start(): 启动线程
  - run(): 定义线程任务
  - sleep(long millis): 使线程休眠
  - join(): 等待线程结束
  - yield(): 让出CPU执行权

```java
// 方法1：继承Thread类
class MyThread extends Thread {
    public void run() {
        // 线程执行代码
    }
}

// 方法2：实现Runnable接口
class MyRunnable implements Runnable {
    public void run() {
        // 线程执行代码
    }
}
```

线程生命周期:  
- 新建（New）
- 可运行（Runnable）
- 运行（Running）
- 阻塞（Blocked）
- 等待（Waiting）
- 超时等待（Timed Waiting）
- 终止（Terminated）

线程池: 
- Executors 工厂方法
- ThreadPoolExecutor 自定义线程池

```java
ExecutorService executor = Executors.newFixedThreadPool(10);
executor.submit(new Runnable() {
    public void run() {
        // 任务代码
    }
});
```

## 网络编程

### TCP

- server
- client

### UDP

- server
- client

## 端口扫描

## GUI

## 练习

- 进程遍历程序：遍历进程名&id，用GUI展示
- 端口扫描器：对目标的指定IP&端口范围进行扫描，用GUI展示
- TCP聊天功能：由客户端及服务端进行通信，相互发送数据
