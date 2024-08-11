# Java

## Java程序的编译和运行

Java 是一种编译型和解释型结合的编程语言，具有“编写一次，随处运行”的特性。Java 程序的编译和运行过程主要包括以下几个步骤：编写源代码、编译源代码、执行字节码以及在 Java 虚拟机（JVM）中运行程序。以下是详细的介绍：

### 1. Java 编译原理概述
Java 的编译过程与传统的编译型语言（如 C 或 C++）有所不同。Java 程序首先被编译成一种与平台无关的中间代码，称为字节码（Bytecode）。这些字节码文件可以在任何安装了 Java 虚拟机（JVM）的设备上运行，而不需要重新编译。

### 2. Java 程序的编写与编译
#### 2.1 编写源代码
- Java 程序首先以 `.java` 文件的形式编写，这些文件包含了 Java 的源代码。
- 每个 `.java` 文件通常定义一个类或接口，文件名通常与类名相同。

例如，以下是一个简单的 Java 源代码文件 `HelloWorld.java`：
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

#### 2.2 编译源代码
- 使用 Java 编译器 `javac` 编译 `.java` 源文件。
- 编译器将 Java 源代码编译成字节码，并生成一个或多个 `.class` 文件。每个 `.class` 文件包含一个类或接口的字节码。

```bash
javac HelloWorld.java
```
执行上述命令后，会生成一个 `HelloWorld.class` 文件。

- **字节码（Bytecode）**:
  - 字节码是一种中间代码，介于源代码和机器码之间。
  - 它是与平台无关的，因此可以在任何支持 Java 的平台上运行。

### 3. Java 程序的运行

#### 3.1 Java 虚拟机（JVM）
- **JVM 的作用**:
  - Java 虚拟机（JVM）是运行 Java 程序的虚拟计算机，它负责将字节码解释并执行。
  - JVM 是与平台相关的，但字节码是与平台无关的。每种操作系统都有自己的 JVM 实现。

- **JVM 的结构**:
  - **类加载器（Class Loader）**: 负责加载字节码文件到内存中。
  - **执行引擎（Execution Engine）**: 负责解释或即时编译（JIT）字节码，并执行相应的指令。
  - **垃圾收集器（Garbage Collector）**: 负责自动管理内存，回收不再使用的对象。

#### 3.2 执行 Java 程序
- 使用 Java 命令 `java` 运行编译后的字节码文件。

```bash
java HelloWorld
```
执行上述命令后，JVM 加载 `HelloWorld.class` 文件，并执行 `main` 方法中的代码，输出结果为 `Hello, World!`。

### 4. 编译和运行过程的详细步骤

1. **编译过程**:
   - Java 源代码编写完成后，使用 `javac` 编译器将 `.java` 文件编译为 `.class` 文件（字节码文件）。
   - 编译器进行词法分析、语法分析、语义分析，生成抽象语法树（AST），并进一步转换为字节码。

2. **加载过程**:
   - JVM 的类加载器读取 `.class` 文件，将字节码加载到内存中。
   - 类加载器验证字节码的正确性，并将其转换为 JVM 内部的数据结构。

3. **解释或即时编译**:
   - JVM 的执行引擎通过解释器逐条解释字节码指令，并将其转换为机器指令执行。
   - 为了提高性能，JVM 还可以使用即时编译器（Just-In-Time Compiler, JIT），将热点代码直接编译为本地机器码，从而加速执行。

4. **执行过程**:
   - JVM 执行已经加载的字节码，按照程序的逻辑执行相应的指令。
   - JVM 同时管理内存，通过垃圾收集器回收无用的对象，避免内存泄漏。

### 5. 平台无关性的实现
- **字节码的可移植性**:
  - Java 的核心在于它的字节码是与平台无关的。编译后的 `.class` 文件可以在任何安装了 JVM 的设备上运行。
  - 这实现了“编写一次，到处运行”（Write Once, Run Anywhere）的目标。

- **JVM 的平台依赖性**:
  - 虽然字节码是可移植的，但 JVM 是与平台相关的。不同操作系统和硬件平台都有相应的 JVM 实现，用于将字节码转换为本地机器码。

### 6. 总结
Java 程序的编译和运行过程由源代码编写、编译、加载、解释/编译执行等步骤组成。Java 的平台无关性主要通过字节码和 JVM 实现，使得编写的程序可以跨平台运行。这种设计使得 Java 成为一种强大且广泛应用的编程语言，特别适合需要跨平台兼容的应用开发。

## Java版本

Java 是一门历史悠久的编程语言，自 1995 年首次发布以来，已经发展了多个版本，以适应不同的开发需求。Java 的主要版本可以分为两个：Java SE（Standard Edition）和 Java EE（Enterprise Edition）。下面是对这两个主要版本的详细介绍。

### 1. Java SE (Java Standard Edition)

#### 1.1 Java SE 的概述
Java SE 是 Java 平台的标准版本，包含了开发桌面应用程序、控制台应用程序、和简单服务器应用程序的核心 API。它提供了基本的编程工具和库，是所有 Java 应用的基础。

#### 1.2 Java SE 的主要组件
- **核心库（Core Libraries）**:
  - 包含 Java 语言的基础类，如 `java.lang`、`java.util`、`java.io` 等。这些类提供了数据结构、I/O 操作、字符串处理、正则表达式、多线程等核心功能。
  
- **Java 运行时环境 (JRE)**:
  - JRE 是用于运行 Java 应用的环境，包含了 Java 虚拟机 (JVM) 和 Java 核心类库。

- **Java 开发工具包 (JDK)**:
  - JDK 包含了 JRE 以及用于编写、编译和调试 Java 应用的开发工具，如 `javac`（编译器）、`javadoc`（文档生成器）、`jdb`（调试器）等。

- **Swing 和 AWT**:
  - 用于开发图形用户界面 (GUI) 的库。Swing 提供了更现代化的组件，而 AWT 是较为底层的图形库。

- **JavaFX**:
  - 一个用于构建富客户端应用程序的库，主要用于替代 Swing，以更现代和灵活的方式来构建图形用户界面。

- **Java 虚拟机 (JVM)**:
  - JVM 是 Java SE 的核心组件，它将 Java 的字节码解释或即时编译成机器码，并在目标平台上执行。

#### 1.3 Java SE 的版本演进
Java SE 随着时间的推移不断演进，引入了许多新特性和改进。从 Java 1.0 开始，到最新的 Java 21，每个版本都带来了新的 API 和语言特性。例如：
- **Java 5 (J2SE 5.0)**: 引入泛型、增强型 for 循环、枚举类型和自动装箱/拆箱等特性。
- **Java 8**: 引入了 lambda 表达式、流 API、默认方法等功能，是 Java 语言的一次重大更新。
- **Java 9**: 引入模块化系统 (Project Jigsaw)，重组了 JDK 代码库。
- **Java 17**: 这是一个长期支持（LTS）版本，包含了许多语言特性的进一步完善，如 `sealed classes`。

### 2. Java EE (Java Enterprise Edition)

#### 2.1 Java EE 的概述
Java EE 是 Java 平台的企业版，专门为开发企业级应用程序（如大型分布式系统、Web 服务、和企业应用集成）而设计。它是在 Java SE 的基础上扩展的，增加了许多用于处理复杂业务逻辑、大规模数据和分布式系统的 API 和工具。

#### 2.2 Java EE 的主要组件
- **Servlet 和 JSP**:
  - Servlet 是 Java EE 中用于处理 HTTP 请求和响应的服务器端组件，JSP（JavaServer Pages）是用于构建动态 Web 页面的一种技术。

- **Enterprise JavaBeans (EJB)**:
  - EJB 是 Java EE 中用于构建分布式企业应用程序的组件模型，支持事务处理、安全管理和远程调用等功能。

- **Java Persistence API (JPA)**:
  - JPA 是 Java EE 提供的一种对象关系映射 (ORM) 规范，简化了数据库的访问和持久化操作。

- **Java Message Service (JMS)**:
  - JMS 是用于消息传递的 API，支持异步消息的发送和接收，常用于企业级消息系统中。

- **Java API for RESTful Web Services (JAX-RS)**:
  - JAX-RS 提供了创建 RESTful Web 服务的 API，使得 Java EE 应用可以通过 HTTP 协议与外部系统交互。

- **Java API for XML Web Services (JAX-WS)**:
  - JAX-WS 是用于创建 SOAP Web 服务的 API，支持基于 XML 的消息传递。

#### 2.3 Java EE 的发展与 Jakarta EE
- **Java EE 到 Jakarta EE**:
  - 在 2017 年，Java EE 的管理权从 Oracle 转移到 Eclipse 基金会，并更名为 Jakarta EE。虽然核心的概念和组件保持不变，但 Jakarta EE 开始更加开放和社区驱动的发展。

- **Java EE 的典型应用**:
  - Java EE 广泛用于银行、电子商务、企业管理系统等需要高可用性、高可靠性和可扩展性的领域。

### 3. Java SE 与 Java EE 的关系
- **Java SE 是基础**: Java EE 是在 Java SE 基础上构建的。Java SE 提供了核心语言功能和标准库，而 Java EE 扩展了这些功能，以支持大规模的企业级应用。
  
- **适用场景不同**: Java SE 主要用于桌面应用、控制台程序和小型服务器端应用的开发；Java EE 则专注于大型企业应用的开发，提供了强大的分布式计算、事务管理和安全支持。

### 4. 总结
Java SE 和 Java EE 是 Java 平台的两个主要版本，分别适用于不同的开发需求。Java SE 提供了核心的编程工具和库，适用于大多数 Java 应用程序的开发。Java EE 则在 Java SE 的基础上扩展了许多企业级功能，专门用于开发复杂的分布式系统和企业级应用。通过理解这两个版本的区别和用途，开发者可以选择最适合其项目需求的 Java 平台。

## JDK

### 1. 什么是 JDK？

JDK（Java Development Kit）是 Java 编程语言的开发工具包，是 Java 平台的核心组成部分。JDK 提供了一系列工具和库，帮助开发者编写、编译、调试和运行 Java 程序。JDK 是 Java 开发的基础环境，没有它，开发者无法进行 Java 程序的开发和调试。

#### 1.1 JDK 的组成部分

- **Java 编译器 (`javac`)**:
  - `javac` 是 JDK 中的编译器工具，用于将 Java 源代码（.java 文件）编译成字节码文件（.class 文件）。
  
- **Java 运行时环境 (JRE)**:
  - JDK 包含了一个完整的 Java 运行时环境 (JRE)，它包括 Java 虚拟机 (JVM) 和 Java 标准类库。这意味着 JDK 既可以用来开发程序，也可以用来运行 Java 程序。
  
- **Java 虚拟机 (JVM)**:
  - JVM 是 Java 程序的运行时环境，它将编译后的字节码解释或即时编译为机器代码并执行。JVM 是 JDK 和 JRE 的核心组件。

- **标准类库**:
  - JDK 包含了一组 Java SE 标准类库，这些库提供了丰富的功能，如数据结构、文件操作、网络通信、图形用户界面等。
  
- **开发工具**:
  - 除了 `javac` 编译器外，JDK 还包括一系列开发工具，如：
    - `javadoc`：用于生成 Java API 文档。
    - `jdb`：Java 调试器，用于调试 Java 应用程序。
    - `jar`：用于打包和管理 JAR 文件。
    - `javap`：用于反编译和分析字节码文件。

#### 1.2 JDK 的版本

JDK 的版本通常与 Java SE 的版本一致。例如，JDK 8 对应 Java SE 8，JDK 11 对应 Java SE 11。每个 JDK 版本都会随着 Java SE 的版本更新而引入新的特性和改进。

### 2. JDK 与 Java SE 的区别

- **Java SE 是规范，JDK 是实现**：
  - Java SE 是一种规范，定义了 Java 语言和类库的标准。它描述了一个完整的 Java 语言平台，包括所有的核心 API 和 JVM 的规范。
  - JDK 是 Java SE 规范的具体实现。JDK 提供了实现这些规范的工具和库，使开发者能够基于 Java SE 进行开发。

- **Java SE 是基础，JDK 是工具**：
  - Java SE 提供了 Java 语言的基础类库和 API，如集合框架、I/O 库、并发库等。它定义了开发 Java 应用的核心功能。
  - JDK 则是包含这些类库的开发工具包，提供了创建、编译、调试和执行 Java 程序的所有必要工具。

### 3. JDK 与 Java EE 的区别

- **Java EE 是企业级平台，JDK 是开发工具**：
  - Java EE（现在称为 Jakarta EE）是一个企业级 Java 平台，扩展了 Java SE 的功能，增加了用于开发分布式系统、Web 应用和企业级应用的 API 和库。
  - JDK 是一个开发工具包，用于编写、编译和调试 Java 程序。虽然 JDK 是开发 Java EE 应用的基础，但它不包含 Java EE 的企业级库和 API。

- **Java EE 需要额外的服务器支持**：
  - Java EE 的功能通常需要在支持 Java EE 的应用服务器（如 Apache Tomcat、WildFly 或 GlassFish）上运行。这些服务器提供了对 Java EE 规范的支持，如 Servlet、JSP、EJB 等。
  - JDK 主要用于开发和运行标准的 Java 应用程序，而不包含 Java EE 的服务器端功能。

### 4. 总结

- **JDK** 是 Java 的开发工具包，包含了开发和运行 Java 应用所需的所有工具和库。它是 Java 开发者必备的工具，包含了 Java 编译器、JVM、标准类库和其他开发工具。
  
- **Java SE** 是一个规范，定义了标准的 Java 类库和 JVM 的行为。JDK 是 Java SE 的具体实现，是开发 Java SE 应用的基础。

- **Java EE**（Jakarta EE） 是在 Java SE 之上构建的企业级平台，专注于开发大型分布式系统和企业应用。JDK 是开发 Java EE 应用所需的基础工具，但 Java EE 还需要额外的库和服务器支持。

理解 JDK、Java SE 和 Java EE 之间的关系有助于开发者更好地选择和使用适合其项目需求的 Java 平台和工具。

# Java语言基础

## 输入输出流

在 Java 中，输入输出流是与外部环境（如控制台、文件、网络等）进行数据交换的基础。对于控制台输入，Java 提供了 `Scanner` 类，而对于控制台输出，通常使用 `System.out.println`。下面详细介绍 `Scanner` 类的各种使用方法，以及 `System.out.println` 的使用。

### 1. `Scanner` 类的介绍

`Scanner` 类是 Java 中用于从各种输入源（如控制台、文件、字符串等）读取数据的实用工具。它位于 `java.util` 包中，通常用于处理简单的控制台输入。

#### 1.1 `Scanner` 的基本使用
使用 `Scanner` 读取控制台输入时，通常通过 `System.in` 创建一个 `Scanner` 对象：

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter something:");
        String input = scanner.nextLine();  // 读取整行输入
        System.out.println("You entered: " + input);
    }
}
```

#### 1.2 `Scanner` 类常用方法

- **读取字符串**:
  - `nextLine()`: 读取整行输入，包括空格和回车。
  - `next()`: 读取输入的下一个标记（以空格、换行符或制表符作为分隔符）。

  ```java
  String line = scanner.nextLine();  // 读取整行
  String word = scanner.next();      // 读取下一个单词
  ```

- **读取基本数据类型**:
  - `nextInt()`: 读取 `int` 类型的整数。
  - `nextDouble()`: 读取 `double` 类型的小数。
  - `nextFloat()`: 读取 `float` 类型的小数。
  - `nextLong()`: 读取 `long` 类型的整数。
  - `nextBoolean()`: 读取布尔值 (`true` 或 `false`)。

  ```java
  int number = scanner.nextInt();       // 读取整数
  double decimal = scanner.nextDouble(); // 读取小数
  boolean bool = scanner.nextBoolean();  // 读取布尔值
  ```

- **读取字符**:
  `Scanner` 类没有直接读取单个字符的方法，但可以通过读取字符串并提取第一个字符来实现。

  ```java
  char character = scanner.next().charAt(0);  // 读取输入的第一个字符
  ```

- **读取数组**:
  可以使用 `Scanner` 循环读取多个值来填充数组。

  ```java
  int[] numbers = new int[5];
  for (int i = 0; i < numbers.length; i++) {
      numbers[i] = scanner.nextInt();  // 依次读取整数存入数组
  }
  ```

- **判断是否有更多输入**:
  - `hasNext()`: 检查是否有更多输入。
  - `hasNextInt()`, `hasNextDouble()`: 检查下一个输入是否为特定类型。

  ```java
  if (scanner.hasNextInt()) {
      int number = scanner.nextInt();
  }
  ```

#### 1.3 关闭 `Scanner`
使用 `Scanner` 读取数据后，应调用 `close()` 方法关闭它以释放资源，特别是在读取文件或网络流时。

```java
scanner.close();
```

### 2. `System.out.println` 的使用

`System.out.println` 是 Java 中最常用的输出语句，用于向控制台打印信息并换行。

#### 2.1 基本用法

- **打印字符串**:
  ```java
  System.out.println("Hello, World!");
  ```

- **打印数值**:
  ```java
  int num = 10;
  System.out.println(num);  // 输出: 10
  ```

- **打印字符**:
  ```java
  char ch = 'A';
  System.out.println(ch);  // 输出: A
  ```

- **打印布尔值**:
  ```java
  boolean flag = true;
  System.out.println(flag);  // 输出: true
  ```

#### 2.2 格式化输出
如果需要更复杂的格式，可以使用 `System.out.printf()` 或 `String.format()` 方法。

```java
int x = 10;
double y = 20.5;
System.out.printf("x = %d, y = %.2f", x, y);  // 输出: x = 10, y = 20.50
```

### 3. 总结
- `Scanner` 类是处理用户输入的强大工具，可以轻松读取各种类型的数据。
- `System.out.println` 是最常用的输出语句，用于将信息打印到控制台。通过灵活使用这些方法，Java 程序可以有效地进行用户交互和输出显示。

## 基本数据

### 1. 整型数据类型
整型数据类型用于表示整数，Java 提供了四种整型数据类型，分别是 `byte`、`short`、`int` 和 `long`。

#### 1.1 `byte`
- **定义**: `byte` 是最小的整型数据类型，占用 1 个字节（8 位）。
- **范围**: -128 到 127。
- **使用**:
    ```java
    byte a = 10;  // 初始化并赋值
    byte b = -20;
    ```
- **注意事项**: 由于范围较小，通常用于节省内存，特别是在大数组中。

#### 1.2 `short`
- **定义**: `short` 占用 2 个字节（16 位）。
- **范围**: -32,768 到 32,767。
- **使用**:
    ```java
    short c = 30000;
    short d = -20000;
    ```
- **注意事项**: 相比 `int`，`short` 也较少使用，更多用于节省内存。

#### 1.3 `int`
- **定义**: `int` 是最常用的整型数据类型，占用 4 个字节（32 位）。
- **范围**: -2^31 到 2^31-1，即 -2,147,483,648 到 2,147,483,647。
- **使用**:
    ```java
    int e = 100000;  // 初始化并赋值
    int f = -500000;
    ```
- **注意事项**: `int` 是 Java 中默认的整数类型，通常在不需要特定类型时使用。

#### 1.4 `long`
- **定义**: `long` 占用 8 个字节（64 位），用于表示较大范围的整数。
- **范围**: -2^63 到 2^63-1，即 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807。
- **使用**:
    ```java
    long g = 10000000000L;  // 初始化并赋值，L 表示是 long 类型的字面量
    long h = -20000000000L;
    ```
- **注意事项**: 如果需要表示超过 `int` 范围的整数，使用 `long`。

### 2. 浮点型数据类型
浮点型数据类型用于表示带有小数点的数字，Java 提供了两种浮点型数据类型：`float` 和 `double`。

#### 2.1 `float`
- **定义**: `float` 占用 4 个字节（32 位）。
- **范围**: 约为 3.4e−038 到 3.4e+038，精度约为 6 到 7 位十进制数。
- **使用**:
    ```java
    float i = 5.75f;  // 初始化并赋值，f 表示是 float 类型的字面量
    float j = -3.14f;
    ```
- **注意事项**: 通常用于节省内存或在科学计算中。

#### 2.2 `double`
- **定义**: `double` 占用 8 个字节（64 位），是 Java 中默认的浮点型数据类型。
- **范围**: 约为 1.7e−308 到 1.7e+308，精度约为 15 位十进制数。
- **使用**:
    ```java
    double k = 19.99;  // 初始化并赋值
    double l = -100.01;
    ```
- **注意事项**: `double` 是 Java 中的默认浮点型类型，通常在需要更高精度时使用。

### 3. 字符型数据类型
#### 3.1 `char`
- **定义**: `char` 是一个字符类型，占用 2 个字节（16 位），用于表示单个字符。
- **范围**: 0 到 65,535 (0 到 2^16-1) 的 Unicode 值。
- **使用**:
    ```java
    char m = 'A';  // 初始化并赋值
    char n = '\u0041';  // 使用 Unicode 表示
    ```
- **注意事项**: `char` 使用单引号表示字符，支持 Unicode 编码，因此可以表示全球多种语言的字符。

### 4. 布尔型数据类型
#### 4.1 `boolean`
- **定义**: `boolean` 只有两个值，`true` 和 `false`，占用 1 位（实际存储实现可能不同）。
- **范围**: `true` 或 `false`。
- **使用**:
    ```java
    boolean o = true;  // 初始化并赋值
    boolean p = false;
    ```
- **注意事项**: 布尔型通常用于条件判断和逻辑控制。

### 5. 数据类型的默认值

在 Java 中，当一个变量被声明但没有被显式初始化时，它将被赋予一个默认值。不同的数据类型有不同的默认值。这些默认值在类成员变量（实例变量和静态变量）中起作用，而局部变量则没有默认值，必须在使用前显式初始化。

#### 1. 基本数据类型的默认值

Java 提供了八种基本数据类型，每种类型在未初始化时都有一个特定的默认值。

- **`byte`**: 默认值为 `0`
- **`short`**: 默认值为 `0`
- **`int`**: 默认值为 `0`
- **`long`**: 默认值为 `0L`
- **`float`**: 默认值为 `0.0f`
- **`double`**: 默认值为 `0.0d`
- **`char`**: 默认值为 `'\u0000'` (null字符，值为 0)
- **`boolean`**: 默认值为 `false`

**示例：**
```java
public class DefaultValues {
    byte defaultByte;
    short defaultShort;
    int defaultInt;
    long defaultLong;
    float defaultFloat;
    double defaultDouble;
    char defaultChar;
    boolean defaultBoolean;

    public static void main(String[] args) {
        DefaultValues dv = new DefaultValues();
        
        System.out.println("Default byte: " + dv.defaultByte);
        System.out.println("Default short: " + dv.defaultShort);
        System.out.println("Default int: " + dv.defaultInt);
        System.out.println("Default long: " + dv.defaultLong);
        System.out.println("Default float: " + dv.defaultFloat);
        System.out.println("Default double: " + dv.defaultDouble);
        System.out.println("Default char: '" + dv.defaultChar + "'");
        System.out.println("Default boolean: " + dv.defaultBoolean);
    }
}
```
在这个例子中，所有的基本数据类型在没有被显式初始化时，均会被赋予它们各自的默认值。

#### 2. 引用数据类型的默认值

引用数据类型包括类、接口、数组等。当引用数据类型的变量没有被显式初始化时，默认值为 `null`。

**示例：**
```java
public class DefaultReference {
    String defaultString;
    int[] defaultArray;

    public static void main(String[] args) {
        DefaultReference dr = new DefaultReference();
        
        System.out.println("Default String: " + dr.defaultString); // 输出 null
        System.out.println("Default Array: " + dr.defaultArray); // 输出 null
    }
}
```
在这个例子中，`String` 和 `int[]` 数组类型的变量在未初始化时，它们的默认值为 `null`。

#### 3. 局部变量的默认值

局部变量在方法内部声明，必须在使用前显式初始化，否则会导致编译错误。局部变量没有默认值，Java 编译器要求在使用局部变量前对其进行显式赋值。

**示例：**
```java
public class LocalVariableTest {
    public static void main(String[] args) {
        int localVar;
        // System.out.println(localVar); // 编译错误，变量 localVar 未初始化
    }
}
```
在这个例子中，`localVar` 是一个局部变量，未被初始化就尝试访问它将导致编译错误。

### 6.Java 数据类型转换

在 Java 编程中，数据类型转换是一个常见的操作，尤其是在需要将不同类型的变量进行操作时。Java 提供了多种转换方式，包括隐式转换、显式转换、以及字符串与其他基本数据类型之间的转换。下面将详细介绍这些转换方式。

#### 1. 隐式转换（自动类型转换）

隐式转换是指 Java 编译器在某些条件下自动将一种较小的数据类型转换为一种较大的数据类型。这种转换是安全的，因为不会发生数据的丢失。

**自动转换顺序：**
- `byte` → `short` → `int` → `long` → `float` → `double`
- `char` → `int` → `long` → `float` → `double`

**示例：**
```java
public class ImplicitConversion {
    public static void main(String[] args) {
        int intVal = 42;
        double doubleVal = intVal; // int 自动转换为 double
        
        System.out.println("Int Value: " + intVal);
        System.out.println("Double Value: " + doubleVal);
    }
}
```
在这个例子中，`int` 类型的 `intVal` 自动转换为 `double` 类型的 `doubleVal`。

#### 2. 显式转换（强制类型转换）

显式转换是指将一种较大的数据类型转换为一种较小的数据类型。由于这种转换可能导致数据丢失，因此需要使用显式的转换操作来进行。

**示例：**
```java
public class ExplicitConversion {
    public static void main(String[] args) {
        double doubleVal = 9.78;
        int intVal = (int) doubleVal; // double 强制转换为 int

        System.out.println("Double Value: " + doubleVal);
        System.out.println("Int Value: " + intVal);
    }
}
```
在这个例子中，`double` 类型的 `doubleVal` 被强制转换为 `int` 类型的 `intVal`，小数部分被截断。

#### 3. 字符串与基本数据类型的转换

在 Java 中，字符串可以很方便地与其他基本数据类型相互转换。Java 提供了一些内置的方法来实现这些转换。

##### 3.1 基本数据类型转换为字符串

**示例：**
```java
public class BasicToString {
    public static void main(String[] args) {
        int intVal = 123;
        double doubleVal = 456.78;
        String intStr = Integer.toString(intVal);
        String doubleStr = Double.toString(doubleVal);

        System.out.println("String from int: " + intStr);
        System.out.println("String from double: " + doubleStr);
    }
}
```
在这个例子中，`int` 和 `double` 类型的变量被转换为字符串。

##### 3.2 字符串转换为基本数据类型

**示例：**
```java
public class StringToBasic {
    public static void main(String[] args) {
        String intStr = "123";
        String doubleStr = "456.78";

        int intVal = Integer.parseInt(intStr);
        double doubleVal = Double.parseDouble(doubleStr);

        System.out.println("Int from String: " + intVal);
        System.out.println("Double from String: " + doubleVal);
    }
}
```
在这个例子中，字符串 `intStr` 和 `doubleStr` 被转换为 `int` 和 `double` 类型。

#### 4. 字符与整数之间的转换

字符和整数之间的转换也很常见，`char` 类型可以自动转换为 `int` 类型，而 `int` 类型转换为 `char` 类型则需要显式转换。

**示例：**
```java
public class CharIntConversion {
    public static void main(String[] args) {
        char charVal = 'A';
        int intVal = charVal;  // char 自动转换为 int
        System.out.println("Int Value: " + intVal); // 输出 65

        intVal = 66;
        charVal = (char) intVal;  // int 强制转换为 char
        System.out.println("Char Value: " + charVal); // 输出 'B'
    }
}
```
在这个例子中，`char` 类型的 `charVal` 自动转换为 `int` 类型，表示字符的 ASCII 值。而将 `int` 类型转换为 `char` 时，输出对应的字符。

### Java 中的进制数相关内容

> 在 Java 编程中，进制数的表示和转换是一个重要的知识点。Java 支持多种进制的整数表示，包括二进制、八进制、十进制和十六进制。以下是关于 Java 中进制数的详细介绍，包括表示方式、转换方法及示例代码。

- 十进制：十进制的表现形式大家都很熟悉，如120、0、-127。除了数字0，不能以0作为其他十进制数的开头。
- 八进制：如0123（转换成十进制数为83）、-0123（转换成十进制数为-83）。八进制数必须以0开头。
- 十六进制：如0x25（转换成十进制数为37）、0Xb01e（转换成十进制数为45086）。十六进制数必须以0X或0x开头。

#### 1. 整数的进制表示

Java 支持以下几种整数进制表示方式：

- **十进制（Decimal）**：最常用的进制，基数为 10。
- **二进制（Binary）**：基数为 2，使用 `0b` 或 `0B` 前缀表示。
- **八进制（Octal）**：基数为 8，使用 `0` 前缀表示。
- **十六进制（Hexadecimal）**：基数为 16，使用 `0x` 或 `0X` 前缀表示。

**示例：**
```java
public class NumberBaseExample {
    public static void main(String[] args) {
        int decimal = 255;       // 十进制
        int binary = 0b11111111; // 二进制
        int octal = 0377;        // 八进制
        int hexadecimal = 0xFF;  // 十六进制

        System.out.println("Decimal: " + decimal);           // 输出 255
        System.out.println("Binary: " + binary);             // 输出 255
        System.out.println("Octal: " + octal);               // 输出 255
        System.out.println("Hexadecimal: " + hexadecimal);   // 输出 255
    }
}
```

#### 2. 进制转换

Java 提供了多种方法来将不同进制的整数进行转换。

**2.1 从十进制转换为其他进制**

使用 `Integer` 类中的 `toBinaryString`、`toOctalString` 和 `toHexString` 方法可以将十进制整数转换为二进制、八进制和十六进制字符串。

**示例：**
```java
public class BaseConversion {
    public static void main(String[] args) {
        int number = 255;

        String binary = Integer.toBinaryString(number);
        String octal = Integer.toOctalString(number);
        String hexadecimal = Integer.toHexString(number);

        System.out.println("Binary: " + binary);           // 输出 11111111
        System.out.println("Octal: " + octal);             // 输出 377
        System.out.println("Hexadecimal: " + hexadecimal); // 输出 ff
    }
}
```

**2.2 从其他进制转换为十进制**

使用 `Integer` 类中的 `parseInt` 方法可以将二进制、八进制和十六进制字符串转换为十进制整数。需要指定原始字符串的进制。

**示例：**
```java
public class BaseConversion {
    public static void main(String[] args) {
        String binaryStr = "11111111";
        String octalStr = "377";
        String hexadecimalStr = "ff";

        int binary = Integer.parseInt(binaryStr, 2);
        int octal = Integer.parseInt(octalStr, 8);
        int hexadecimal = Integer.parseInt(hexadecimalStr, 16);

        System.out.println("Binary to Decimal: " + binary);           // 输出 255
        System.out.println("Octal to Decimal: " + octal);             // 输出 255
        System.out.println("Hexadecimal to Decimal: " + hexadecimal); // 输出 255
    }
}
```

#### 3. 字符串进制转换

在某些情况下，可能需要将字符串表示的数字转换为不同进制的整数。可以使用 `Integer.parseInt` 方法将字符串转换为十进制整数，然后使用 `Integer.toBinaryString`、`Integer.toOctalString` 或 `Integer.toHexString` 方法获取其他进制的字符串表示。

**示例：**
```java
public class StringBaseConversion {
    public static void main(String[] args) {
        String decimalStr = "255";

        int decimal = Integer.parseInt(decimalStr);
        String binary = Integer.toBinaryString(decimal);
        String octal = Integer.toOctalString(decimal);
        String hexadecimal = Integer.toHexString(decimal);

        System.out.println("Decimal: " + decimalStr);
        System.out.println("Binary: " + binary);
        System.out.println("Octal: " + octal);
        System.out.println("Hexadecimal: " + hexadecimal);
    }
}
```

#### 4. 浮点数进制表示

Java 中浮点数（`float` 和 `double`）也支持十进制和科学计数法的表示，但不支持其他进制的直接表示。在代码中通常使用科学计数法表示浮点数，如 `1.23e4` 表示 \(1.23 \times 10^4\)。

**示例：**
```java
public class FloatingPointExample {
    public static void main(String[] args) {
        double scientific = 1.23e4; // 1.23 * 10^4 = 12300.0
        System.out.println("Scientific Notation: " + scientific); // 输出 12300.0
    }
}
```

#### 5. 进制运算

Java 中的进制运算通常涉及对整数进行基本的算术运算。无论输入是哪个进制，算术运算都使用标准的二进制补码形式。结果可以通过 `Integer.toBinaryString`、`Integer.toOctalString` 和 `Integer.toHexString` 方法来查看不同进制下的结果。

**示例：**
```java
public class BaseArithmetic {
    public static void main(String[] args) {
        int num1 = 0b1010;  // 二进制 1010 = 十进制 10
        int num2 = 0xA;     // 十六进制 A = 十进制 10
        int sum = num1 + num2;
        int product = num1 * num2;

        System.out.println("Sum in Decimal: " + sum);               // 输出 20
        System.out.println("Sum in Binary: " + Integer.toBinaryString(sum)); // 输出 10100
        System.out.println("Sum in Octal: " + Integer.toOctalString(sum));   // 输出 24
        System.out.println("Sum in Hexadecimal: " + Integer.toHexString(sum)); // 输出 14

        System.out.println("Product in Decimal: " + product);         // 输出 100
        System.out.println("Product in Binary: " + Integer.toBinaryString(product)); // 输出 1100100
        System.out.println("Product in Octal: " + Integer.toOctalString(product));   // 输出 144
        System.out.println("Product in Hexadecimal: " + Integer.toHexString(product)); // 输出 64
    }
}
```

#### 总结

Java 提供了多种进制表示和转换的工具。了解不同进制的表示方法及其转换方式，可以帮助开发者在处理各种数据时更有效地进行计算和调试。使用 `Integer` 类的方法来进行进制转换，能够方便地在不同进制之间进行操作，并且了解进制运算中的基本操作将帮助编写更加高效和准确的代码。

### Java 的不同运算符

#### 运算优先级

![java运算优先级](https://s2.loli.net/2023/11/06/ZyAsqB3tKmHSMvi.png)

> Java 提供了丰富的运算符，用于执行各种操作。运算符根据功能分为以下几类：算术运算符、关系运算符、逻辑运算符、位运算符、赋值运算符、条件运算符、以及其他特殊运算符（例如三元运算符、instanceof、和类型转换运算符）。

#### 1. 算术运算符

算术运算符用于执行基本的数学运算，如加、减、乘、除、取余等。

| 运算符 | 描述           | 示例           |
| ------ | -------------- | -------------- |
| `+`    | 加法           | `a + b`        |
| `-`    | 减法           | `a - b`        |
| `*`    | 乘法           | `a * b`        |
| `/`    | 除法           | `a / b`        |
| `%`    | 取余（模运算） | `a % b`        |
| `++`   | 自增           | `a++` 或 `++a` |
| `--`   | 自减           | `a--` 或 `--a` |

**示例：**
```java
public class ArithmeticOperators {
    public static void main(String[] args) {
        int a = 10, b = 20;
        System.out.println("a + b = " + (a + b)); // 输出 30
        System.out.println("a - b = " + (a - b)); // 输出 -10
        System.out.println("a * b = " + (a * b)); // 输出 200
        System.out.println("b / a = " + (b / a)); // 输出 2
        System.out.println("b % a = " + (b % a)); // 输出 0
        
        int c = 5;
        System.out.println("c++ = " + (c++)); // 输出 5, 然后 c 变为 6
        System.out.println("++c = " + (++c)); // 输出 7
    }
}
```

#### 2. 关系运算符

关系运算符用于比较两个值之间的关系，并返回布尔值（`true` 或 `false`）。

| 运算符 | 描述     | 示例     |
| ------ | -------- | -------- |
| `==`   | 等于     | `a == b` |
| `!=`   | 不等于   | `a != b` |
| `>`    | 大于     | `a > b`  |
| `<`    | 小于     | `a < b`  |
| `>=`   | 大于等于 | `a >= b` |
| `<=`   | 小于等于 | `a <= b` |

**示例：**
```java
public class RelationalOperators {
    public static void main(String[] args) {
        int a = 10, b = 20;
        System.out.println("a == b: " + (a == b)); // 输出 false
        System.out.println("a != b: " + (a != b)); // 输出 true
        System.out.println("a > b: " + (a > b));   // 输出 false
        System.out.println("a < b: " + (a < b));   // 输出 true
        System.out.println("a >= b: " + (a >= b)); // 输出 false
        System.out.println("a <= b: " + (a <= b)); // 输出 true
    }
}
```

#### 3. 逻辑运算符

逻辑运算符用于连接布尔表达式，并返回布尔结果。

| 运算符 | 描述   | 示例     |
| ------ | ------ | -------- |
| `&&`   | 逻辑与 | `a && b` |
| `||`   | 逻辑或 | `a || b` |
| `!`    | 逻辑非 | `!a`     |

**示例：**
```java
public class LogicalOperators {
    public static void main(String[] args) {
        boolean a = true, b = false;
        System.out.println("a && b: " + (a && b)); // 输出 false
        System.out.println("a || b: " + (a || b)); // 输出 true
        System.out.println("!a: " + (!a));         // 输出 false
    }
}
```

#### 4. 位运算符

位运算符用于直接操作数据的位级别表示。这些运算符适用于整数类型（`byte`, `short`, `int`, `long`）。

| 运算符 | 描述         | 示例      |
| ------ | ------------ | --------- |
| `&`    | 按位与       | `a & b`   |
| `|`    | 按位或       | `a | b`   |
| `^`    | 按位异或     | `a ^ b`   |
| `~`    | 按位取反     | `~a`      |
| `<<`   | 左移位       | `a << 2`  |
| `>>`   | 右移位       | `a >> 2`  |
| `>>>`  | 无符号右移位 | `a >>> 2` |

**示例：**
```java
public class BitwiseOperators {
    public static void main(String[] args) {
        int a = 5, b = 7;  // 二进制 0101 和 0111
        System.out.println("a & b: " + (a & b)); // 输出 5 (0101)
        System.out.println("a | b: " + (a | b)); // 输出 7 (0111)
        System.out.println("a ^ b: " + (a ^ b)); // 输出 2 (0010)
        System.out.println("~a: " + (~a));       // 输出 -6 (1111...1010)
        System.out.println("a << 1: " + (a << 1)); // 输出 10 (1010)
        System.out.println("a >> 1: " + (a >> 1)); // 输出 2 (0010)
    }
}
```

#### 5. 赋值运算符

赋值运算符用于将值赋给变量。除了基本的赋值运算符（`=`）外，Java 还提供了复合赋值运算符，可以同时进行运算和赋值操作。

| 运算符 | 描述           | 示例       |
| ------ | -------------- | ---------- |
| `=`    | 简单赋值       | `a = b`    |
| `+=`   | 加赋值         | `a += b`   |
| `-=`   | 减赋值         | `a -= b`   |
| `*=`   | 乘赋值         | `a *= b`   |
| `/=`   | 除赋值         | `a /= b`   |
| `%=`   | 取余赋值       | `a %= b`   |
| `&=`   | 按位与赋值     | `a &= b`   |
| `|=`   | 按位或赋值     | `a |= b`   |
| `^=`   | 按位异或赋值   | `a ^= b`   |
| `<<=`  | 左移赋值       | `a <<= b`  |
| `>>=`  | 右移赋值       | `a >>= b`  |
| `>>>=` | 无符号右移赋值 | `a >>>= b` |

**示例：**
```java
public class AssignmentOperators {
    public static void main(String[] args) {
        int a = 10;
        a += 5;  // 等同于 a = a + 5
        System.out.println("a += 5: " + a);  // 输出 15

        a *= 2;  // 等同于 a = a * 2
        System.out.println("a *= 2: " + a);  // 输出 30
    }
}
```

#### 6. 条件运算符（三元运算符）

条件运算符是一种简化的 `if-else` 表达式，用于根据条件选择一个值。

| 运算符 | 描述       | 示例                       |
| ------ | ---------- | -------------------------- |
| `?:`   | 条件表达式 | `result = (a > b) ? a : b` |

**示例：**
```java
public class TernaryOperator {
    public static void main(String[] args) {
        int a = 10, b = 20;
        int max = (a > b) ? a : b;
        System.out.println("Max value: " + max);  // 输出 20
    }
}
```

#### 7. instanceof 运算符

`instanceof` 运算符用于测试一个对象是否是某个特定类或其子类的实例。

**示例：**
```java
public class InstanceofOperator {


    public static void main(String[] args) {
        String str = "Hello, World!";
        boolean result = str instanceof String;
        System.out.println("Is str a String? " + result);  // 输出 true
    }
}
```

#### 8. 类型转换运算符

类型转换运算符用于将一种数据类型转换为另一种数据类型。需要将较大的数据类型转换为较小的类型时必须显式转换。

**示例：**
```java
public class TypeCasting {
    public static void main(String[] args) {
        double d = 9.78;
        int i = (int) d;  // 强制转换 double 为 int
        System.out.println("Converted int: " + i);  // 输出 9
    }
}
```

### Java 整数运算中的注意事项

在 Java 编程中，整数运算是非常常见的操作。虽然整数运算看似简单，但在实际开发中，有一些常见的陷阱和注意事项需要开发者特别留意。这些问题涉及数据类型的范围、溢出、截断、除法运算中的问题，以及类型转换等。

#### 1. 整数溢出（Overflow）

**溢出**发生在当执行运算的结果超过了数据类型所能表示的最大或最小值时。Java 中的整数类型（如 `byte`、`short`、`int`、`long`）都是使用二进制补码表示，因此当发生溢出时，值会“环绕”回到最小值或最大值。

**示例：**
```java
public class IntegerOverflow {
    public static void main(String[] args) {
        int maxInt = Integer.MAX_VALUE;  // 2147483647
        int overflowedInt = maxInt + 1;  // 溢出
        System.out.println("Max int: " + maxInt);         // 输出 2147483647
        System.out.println("Overflowed int: " + overflowedInt); // 输出 -2147483648
    }
}
```

**注意：** Java 并不会在溢出时抛出异常，因此在某些情况下，溢出可能会导致难以发现的错误。

#### 2. 整数截断（Truncation）

**截断**发生在将较大的数据类型强制转换为较小的数据类型时，多余的高位会被舍弃，从而导致数据丢失。

**示例：**
```java
public class IntegerTruncation {
    public static void main(String[] args) {
        long largeValue = 123456789012345L;
        int truncatedValue = (int) largeValue;  // 强制转换
        System.out.println("Original long value: " + largeValue);   // 输出 123456789012345
        System.out.println("Truncated int value: " + truncatedValue); // 可能输出截断后的值
    }
}
```

**注意：** 截断的结果可能会与预期的值相差很大，因此在进行类型转换时要特别小心。

#### 3. 整数除法中的问题

在 Java 中，如果两个整数进行除法运算，结果仍然是整数，并且任何小数部分都会被截断。

**示例：**
```java
public class IntegerDivision {
    public static void main(String[] args) {
        int a = 7;
        int b = 2;
        int result = a / b;
        System.out.println("Integer division result: " + result); // 输出 3
    }
}
```

**注意：** 如果希望得到浮点数结果，应确保至少一个操作数是浮点数（`float` 或 `double`）。

**示例：**
```java
public class FloatingPointDivision {
    public static void main(String[] args) {
        int a = 7;
        int b = 2;
        double result = (double) a / b;
        System.out.println("Floating-point division result: " + result); // 输出 3.5
    }
}
```

#### 4. 模运算（取余）中的注意事项

模运算用于获取两个整数相除后的余数。需要注意的是，模运算的结果与被除数和除数的符号有关。

**示例：**
```java
public class ModulusOperation {
    public static void main(String[] args) {
        int a = 7;
        int b = -3;
        int result1 = a % b;
        int result2 = -a % b;
        System.out.println("7 % -3: " + result1);  // 输出 1
        System.out.println("-7 % -3: " + result2); // 输出 -1
    }
}
```

**注意：** 如果操作数为负数，模运算结果的符号与被除数相同。

#### 5. 类型提升与表达式计算

在 Java 中，较小的数据类型（`byte`, `short`, `char`）在进行算术运算时会被自动提升为 `int` 类型。这意味着所有参与运算的操作数至少是 `int` 类型。

**示例：**
```java
public class TypePromotion {
    public static void main(String[] args) {
        byte b1 = 10;
        byte b2 = 20;
        byte result = (byte) (b1 + b2);  // 需要强制转换，因为 b1 + b2 的结果是 int
        System.out.println("Result: " + result);  // 输出 30
    }
}
```

**注意：** 在对 `byte`、`short`、`char` 类型的变量进行算术运算时，结果类型为 `int`，因此需要强制转换回原类型。

#### 6. 使用 `Integer` 类进行溢出检查

如果需要在整数运算中进行溢出检查，可以使用 `Integer` 类中的方法，如 `addExact`、`subtractExact`、`multiplyExact` 等，这些方法在溢出时会抛出 `ArithmeticException`。

**示例：**
```java
public class OverflowCheck {
    public static void main(String[] args) {
        try {
            int result = Math.addExact(Integer.MAX_VALUE, 1); // 这里会抛出异常
        } catch (ArithmeticException e) {
            System.out.println("Overflow detected: " + e.getMessage());
        }
    }
}
```

#### 7. `BigInteger` 类处理大数运算

对于可能超出 `long` 范围的大整数，可以使用 `BigInteger` 类进行运算。`BigInteger` 提供了任意精度的整数运算，适用于需要处理极大数值的场景。

**示例：**
```java
import java.math.BigInteger;

public class BigIntegerExample {
    public static void main(String[] args) {
        BigInteger bigInt1 = new BigInteger("12345678901234567890");
        BigInteger bigInt2 = new BigInteger("98765432109876543210");
        BigInteger result = bigInt1.add(bigInt2);
        System.out.println("BigInteger addition result: " + result);
    }
}
```

#### 总结

浮点数运算在 Java 编程中虽然非常实用，但由于浮点数的精度限制和舍入误差，可能会导致一些不可预见的问题。理解这些注意事项并采取适当的措施（如使用容忍误差进行比较、利用 `BigDecimal` 进行高精度计算等）可以帮助在开发过程中减少浮点数相关的错误。

### Java 浮点数运算中的注意事项

浮点数运算在 Java 中用于处理小数值。Java 提供了两种浮点数类型：`float` 和 `double`。`float` 类型是单精度浮点数，`double` 类型是双精度浮点数。尽管浮点数提供了处理小数的能力，但它们在计算中存在一些注意事项和潜在的问题。

#### 1. 浮点数的精度问题

浮点数在计算机内部是以二进制格式存储的，某些十进制小数无法精确表示。这可能导致精度丢失和舍入错误。

**示例：**
```java
public class FloatingPointPrecision {
    public static void main(String[] args) {
        double a = 0.1;
        double b = 0.2;
        double c = a + b;
        System.out.println("0.1 + 0.2 = " + c);  // 输出 0.30000000000000004
    }
}
```

**注意：** 在上述代码中，`0.1` 和 `0.2` 的和并不是精确的 `0.3`，而是 `0.30000000000000004`，这是由于浮点数的表示精度限制造成的。

#### 2. 浮点数比较的误差

由于浮点数的精度问题，直接比较两个浮点数可能会导致不正确的结果。使用 `==` 操作符进行浮点数比较时要小心，通常建议使用一个容忍误差的比较方法。

**示例：**
```java
public class FloatingPointComparison {
    public static void main(String[] args) {
        double a = 0.1 + 0.2;
        double b = 0.3;
        System.out.println("a == b: " + (a == b)); // 输出 false

        // 使用容忍误差的方法比较
        final double EPSILON = 1e-10;
        boolean isEqual = Math.abs(a - b) < EPSILON;
        System.out.println("a is approximately equal to b: " + isEqual); // 输出 true
    }
}
```

**注意：** 在进行浮点数比较时，推荐使用一个非常小的误差值 `EPSILON` 来判断两个浮点数是否“接近”相等。

#### 3. 浮点数的舍入误差

在浮点数运算中，舍入误差是不可避免的。Java 提供了 `Math.round`、`Math.floor` 和 `Math.ceil` 等方法来处理舍入。

**示例：**
```java
public class RoundingErrors {
    public static void main(String[] args) {
        double d = 1.005;
        System.out.println("Rounded: " + Math.round(d * 100) / 100.0); // 输出 1.01
        System.out.println("Floor: " + Math.floor(d * 100) / 100.0);   // 输出 1.00
        System.out.println("Ceil: " + Math.ceil(d * 100) / 100.0);     // 输出 1.01
    }
}
```

**注意：** 在浮点数的舍入运算中，`Math.round` 方法会将值四舍五入到最近的整数，而 `Math.floor` 和 `Math.ceil` 分别会将值向下取整和向上取整。

#### 4. 浮点数的范围和特殊值

`float` 和 `double` 类型有不同的表示范围和特殊值（如正负无穷大、NaN）。要了解这些特殊值如何影响计算结果。

**示例：**
```java
public class FloatingPointSpecialValues {
    public static void main(String[] args) {
        double posInf = Double.POSITIVE_INFINITY;
        double negInf = Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;

        System.out.println("Positive Infinity: " + posInf); // 输出 Infinity
        System.out.println("Negative Infinity: " + negInf); // 输出 -Infinity
        System.out.println("NaN: " + nan); // 输出 NaN

        // 测试 Infinity 和 NaN 的比较
        System.out.println("posInf == posInf: " + (posInf == posInf)); // 输出 true
        System.out.println("nan == nan: " + (nan == nan)); // 输出 false
        System.out.println("nan != nan: " + (nan != nan)); // 输出 true
    }
}
```

**注意：** `Infinity` 和 `NaN` 是特殊的浮点值。`NaN`（Not-a-Number）与任何值（包括自己）的比较结果都为 `false`。`Infinity` 比任何有限数值都大，但 `Infinity` 与 `Infinity` 相等。

#### 5. 浮点数的性能影响

由于浮点运算比整数运算更加复杂，因此浮点数运算可能会影响性能。在高性能计算中，浮点数的精度和性能要求可能需要特别注意。

**注意：** 对于需要高精度和高性能的浮点运算任务，考虑使用更专业的数值库或算法，并在浮点数操作中谨慎处理精度问题。

#### 6. 使用 BigDecimal 进行高精度计算

对于需要高精度的浮点数计算，`BigDecimal` 类提供了比 `float` 和 `double` 更高的精度。`BigDecimal` 可以避免浮点数的精度丢失，但其计算性能相对较低。

**示例：**
```java
import java.math.BigDecimal;

public class BigDecimalExample {
    public static void main(String[] args) {
        BigDecimal bd1 = new BigDecimal("0.1");
        BigDecimal bd2 = new BigDecimal("0.2");
        BigDecimal sum = bd1.add(bd2);
        System.out.println("0.1 + 0.2 = " + sum); // 输出 0.3
    }
}
```

**注意：** `BigDecimal` 支持精确的数学运算，并且允许设置运算的舍入模式，适用于需要高精度计算的场景。

#### 总结

浮点数运算在 Java 编程中虽然非常实用，但由于浮点数的精度限制和舍入误差，可能会导致一些不可预见的问题。理解这些注意事项并采取适当的措施（如使用容忍误差进行比较、利用 `BigDecimal` 进行高精度计算等）可以帮助在开发过程中减少浮点数相关的错误。

### Java 字符串拼接中的注意事项

字符串拼接在 Java 编程中是非常常见的操作。虽然 Java 提供了多种字符串拼接的方法，但在实际应用中，使用这些方法时需要注意一些潜在的问题和最佳实践。下面详细介绍字符串拼接中的注意事项。

#### 1. 使用 `+` 操作符拼接字符串

在 Java 中，使用 `+` 操作符进行字符串拼接是最直观和常见的方法。Java 编译器在编译期间会将多个字符串常量拼接在一起，优化了这些操作。但在运行时，频繁使用 `+` 操作符拼接动态字符串可能会导致性能问题。

**示例：**
```java
public class StringConcatenation {
    public static void main(String[] args) {
        String str1 = "Hello";
        String str2 = "World";
        String result = str1 + " " + str2;
        System.out.println(result);  // 输出 "Hello World"
    }
}
```

**注意事项：**
- **性能问题**：在循环中使用 `+` 操作符拼接字符串时，会频繁创建新的字符串对象。每次拼接都会生成一个新的 `String` 对象，可能会影响性能，特别是在大规模拼接操作时。
- **优化**：编译器会将常量字符串拼接优化为一个单一的字符串常量，但动态拼接仍然会有性能开销。

#### 2. 使用 `StringBuilder` 和 `StringBuffer`

`StringBuilder` 和 `StringBuffer` 是 Java 中处理字符串拼接的推荐工具。这两个类提供了可变的字符序列，通过修改原有对象来拼接字符串，从而避免了频繁创建新的字符串对象，提高了性能。

- **`StringBuilder`**：非线程安全，适用于单线程环境。
- **`StringBuffer`**：线程安全，适用于多线程环境。

**示例：**
```java
public class StringBuilderExample {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder("Hello");
        sb.append(" ");
        sb.append("World");
        String result = sb.toString();
        System.out.println(result);  // 输出 "Hello World"
    }
}
```

**注意事项：**
- **性能**：`StringBuilder` 和 `StringBuffer` 在进行大量字符串拼接时比 `+` 操作符更高效。
- **线程安全**：在多线程环境中，如果需要线程安全的操作，使用 `StringBuffer`，否则可以使用 `StringBuilder`。

#### 3. 使用 `String.format` 进行字符串格式化

`String.format` 方法提供了一种格式化字符串的方式，可以根据指定的格式拼接和插入变量。

**示例：**
```java
public class StringFormatExample {
    public static void main(String[] args) {
        String name = "Alice";
        int age = 30;
        String result = String.format("Name: %s, Age: %d", name, age);
        System.out.println(result);  // 输出 "Name: Alice, Age: 30"
    }
}
```

**注意事项：**
- **格式化**：`String.format` 支持多种格式化选项，使得拼接和格式化结合更加灵活。
- **性能**：虽然 `String.format` 提供了格式化的便利，但在性能敏感的场景中，`StringBuilder` 可能会更加高效。

#### 4. 使用 `String.join` 进行字符串拼接

`String.join` 方法用于将多个字符串用指定的分隔符拼接在一起，适合处理数组或集合中的字符串。

**示例：**
```java
import java.util.Arrays;

public class StringJoinExample {
    public static void main(String[] args) {
        String[] words = {"Hello", "World", "from", "Java"};
        String result = String.join(" ", words);
        System.out.println(result);  // 输出 "Hello World from Java"
    }
}
```

**注意事项：**
- **适用场景**：`String.join` 适合用来拼接数组或集合中的字符串，并指定分隔符。
- **性能**：`String.join` 内部使用 `StringBuilder` 实现，因此在拼接多个字符串时具有较好的性能。

#### 5. 使用 `String.concat` 方法

`String.concat` 方法用于将一个字符串追加到另一个字符串的末尾。

**示例：**
```java
public class StringConcatExample {
    public static void main(String[] args) {
        String str1 = "Hello";
        String str2 = "World";
        String result = str1.concat(" ").concat(str2);
        System.out.println(result);  // 输出 "Hello World"
    }
}
```

**注意事项：**
- **性能**：`String.concat` 方法比 `+` 操作符更高效，但在多个拼接操作中，`StringBuilder` 更为优雅。
- **用途**：适合简单的字符串追加操作。

#### 6. 注意 Unicode 字符串拼接

在处理 Unicode 字符串时，需要注意字符编码和字符的表示，确保拼接结果的正确性。

**示例：**
```java
public class UnicodeConcatenation {
    public static void main(String[] args) {
        String unicodeStr = "\u4F60\u597D";  // 你好
        String greeting = unicodeStr + ", World!";
        System.out.println(greeting);  // 输出 "你好, World!"
    }
}
```

**注意事项：**
- **字符编码**：确保字符串的编码方式一致，以避免乱码。
- **国际化**：在多语言环境中，处理 Unicode 字符串时应特别注意字符的正确显示。

#### 总结

字符串拼接是 Java 编程中经常遇到的任务。了解不同拼接方法的性能影响和适用场景，选择合适的工具和方法，可以帮助提高代码的性能和可维护性。在频繁拼接字符串的场景中，优先考虑使用 `StringBuilder` 或 `StringBuffer`，而对于简单的拼接操作，`+` 操作符和 `String.concat` 方法也可以满足需求。





## 基础语法

### Java 中的 `if` 语句

`if` 语句是 Java 中用于控制程序流程的基本结构之一。它用于根据给定条件的真假来决定是否执行特定的代码块。以下是对 Java 中 `if` 语句的详细介绍，包括基本用法、`if-else`、`if-else if-else` 结构以及嵌套 `if` 语句的用法。

#### 1. 基本 `if` 语句

基本的 `if` 语句用于在条件为 `true` 时执行一段代码。

**语法：**
```java
if (condition) {
    // code to be executed if the condition is true
}
```

**示例：**
```java
public class IfExample {
    public static void main(String[] args) {
        int number = 10;

        if (number > 0) {
            System.out.println("The number is positive."); // 输出 "The number is positive."
        }
    }
}
```

**注意：**
- `condition` 是一个布尔表达式，结果为 `true` 或 `false`。
- 如果条件为 `true`，则执行大括号中的代码块；如果条件为 `false`，则跳过代码块。

#### 2. `if-else` 语句

`if-else` 语句用于在条件为 `true` 时执行一段代码，在条件为 `false` 时执行另一段代码。

**语法：**
```java
if (condition) {
    // code to be executed if the condition is true
} else {
    // code to be executed if the condition is false
}
```

**示例：**
```java
public class IfElseExample {
    public static void main(String[] args) {
        int number = -5;

        if (number >= 0) {
            System.out.println("The number is non-negative.");
        } else {
            System.out.println("The number is negative."); // 输出 "The number is negative."
        }
    }
}
```

#### 3. `if-else if-else` 语句

`if-else if-else` 语句用于处理多个条件。可以设置多个 `else if` 分支来处理不同的条件，并在所有条件都不满足时执行 `else` 块。

**语法：**
```java
if (condition1) {
    // code to be executed if condition1 is true
} else if (condition2) {
    // code to be executed if condition2 is true
} else if (condition3) {
    // code to be executed if condition3 is true
} else {
    // code to be executed if none of the above conditions are true
}
```

**示例：**
```java
public class IfElseIfExample {
    public static void main(String[] args) {
        int score = 85;

        if (score >= 90) {
            System.out.println("Grade: A");
        } else if (score >= 80) {
            System.out.println("Grade: B"); // 输出 "Grade: B"
        } else if (score >= 70) {
            System.out.println("Grade: C");
        } else {
            System.out.println("Grade: D");
        }
    }
}
```

#### 4. 嵌套 `if` 语句

`if` 语句可以嵌套在其他 `if` 语句中，用于处理更复杂的逻辑。

**语法：**
```java
if (condition1) {
    if (condition2) {
        // code to be executed if both condition1 and condition2 are true
    }
}
```

**示例：**
```java
public class NestedIfExample {
    public static void main(String[] args) {
        int age = 25;
        boolean hasID = true;

        if (age >= 18) {
            if (hasID) {
                System.out.println("Access granted."); // 输出 "Access granted."
            } else {
                System.out.println("ID required.");
            }
        } else {
            System.out.println("Access denied.");
        }
    }
}
```

#### 5. 使用条件运算符（`? :`）

条件运算符是 Java 中的一个三元运算符，能够简化简单的 `if-else` 语句。它的语法为：

**语法：**
```java
result = (condition) ? value_if_true : value_if_false;
```

**示例：**
```java
public class TernaryOperatorExample {
    public static void main(String[] args) {
        int number = 10;
        String result = (number % 2 == 0) ? "Even" : "Odd";
        System.out.println("The number is " + result); // 输出 "The number is Even"
    }
}
```

**注意：**
- 条件运算符常用于简化简单的条件判断。

#### 总结

`if` 语句在 Java 中用于控制程序的流程，通过根据条件的真假来执行不同的代码块。理解 `if` 语句的基本用法、`if-else`、`if-else if-else` 结构以及嵌套 `if` 语句的使用，对于编写复杂的逻辑和控制程序的执行非常重要。此外，条件运算符也提供了一种简洁的方式来处理简单的条件判断。

### Java 中的 `switch` 语句

`switch` 语句是 Java 中用于根据不同的条件值执行不同代码块的一种控制结构。它是一种多重分支语句，用于替代多重 `if-else` 语句，可以使代码更加简洁和易于维护。以下是对 Java 中 `switch` 语句的详细介绍，包括基本用法、各部分功能和注意事项。

#### 1. 基本语法

`switch` 语句的基本语法如下：

```java
switch (expression) {
    case value1:
        // code to be executed if expression == value1
        break;
    case value2:
        // code to be executed if expression == value2
        break;
    // more cases...
    default:
        // code to be executed if none of the cases match
}
```

- **expression**：一个整数类型的表达式或枚举类型的变量。
- **case value**：定义条件值，如果 `expression` 的值与 `value` 匹配，则执行该 `case` 下面的代码块。
- **break**：用于退出 `switch` 语句。没有 `break` 的话，程序会继续执行后续的 `case` 语句，直到遇到 `break` 或 `switch` 语句的结束。
- **default**：可选的，指定在所有 `case` 语句都不匹配时执行的代码块。

**示例：**
```java
public class SwitchExample {
    public static void main(String[] args) {
        int day = 3;

        switch (day) {
            case 1:
                System.out.println("Monday");
                break;
            case 2:
                System.out.println("Tuesday");
                break;
            case 3:
                System.out.println("Wednesday"); // 输出 "Wednesday"
                break;
            case 4:
                System.out.println("Thursday");
                break;
            case 5:
                System.out.println("Friday");
                break;
            case 6:
                System.out.println("Saturday");
                break;
            case 7:
                System.out.println("Sunday");
                break;
            default:
                System.out.println("Invalid day"); 
        }
    }
}
```

#### 2. `switch` 支持的数据类型

从 Java 7 开始，`switch` 语句支持使用字符串（`String`）类型的表达式。之前只支持整数类型（`byte`、`short`、`int`）和枚举类型。

**示例（字符串）：**
```java
public class SwitchStringExample {
    public static void main(String[] args) {
        String month = "February";

        switch (month) {
            case "January":
                System.out.println("First month");
                break;
            case "February":
                System.out.println("Second month"); // 输出 "Second month"
                break;
            case "March":
                System.out.println("Third month");
                break;
            default:
                System.out.println("Unknown month");
        }
    }
}
```

#### 3. `switch` 语句的注意事项

- **无 `break` 的情况下**：如果 `case` 语句块中没有 `break`，则会出现“fall-through”现象，即会继续执行后续的 `case` 代码块，直到遇到 `break` 或 `switch` 结束。这种行为在某些情况下是有意为之，但如果不希望这样，应该确保每个 `case` 语句块都包含 `break` 语句。
  
  **示例：**
  ```java
  public class SwitchFallThroughExample {
      public static void main(String[] args) {
          int number = 2;
  
          switch (number) {
              case 1:
                  System.out.println("One");
              case 2:
                  System.out.println("Two"); // 输出 "Two"
              case 3:
                  System.out.println("Three");
                  break;
              default:
                  System.out.println("Not 1, 2, or 3");
          }
      }
  }
  ```
  在上面的示例中，`case 2` 没有 `break`，因此在匹配到 `case 2` 后，程序会继续执行到 `case 3`。

- **`case` 标签必须是常量**：`case` 标签的值必须是编译时常量，不能是变量或表达式。
  
  **示例（错误）：**
  ```java
  int x = 5;
  switch (someVariable) {
      case x: // 错误，x 不是常量
          // code
          break;
  }
  ```

- **可以在 `case` 中使用代码块**：为了避免“fall-through”并将多个 `case` 组合在一起，可以在 `case` 中使用代码块（即 `{}`）。
  
  **示例：**
  ```java
  public class SwitchBlockExample {
      public static void main(String[] args) {
          int number = 3;
  
          switch (number) {
              case 1:
              case 2:
              case 3: {
                  System.out.println("Number is 1, 2, or 3"); // 输出 "Number is 1, 2, or 3"
                  break;
              }
              default:
                  System.out.println("Other number");
          }
      }
  }
  ```

- **`default` 语句是可选的**：`default` 语句在 `switch` 语句中是可选的。当所有的 `case` 标签都不匹配时，`default` 代码块将会执行。如果没有 `default`，并且所有 `case` 都不匹配，则 `switch` 语句不会执行任何操作。

#### 4. `switch` 表达式（Java 12+）

从 Java 12 开始，引入了 `switch` 表达式，使得 `switch` 语句不仅可以用于执行代码块，还可以返回一个值。这种用法使得 `switch` 更加灵活，能够用于赋值和简化代码。

**语法：**
```java
result = switch (expression) {
    case value1 -> result1;
    case value2 -> result2;
    // more cases...
    default -> defaultResult;
};
```

**示例：**
```java
public class SwitchExpressionExample {
    public static void main(String[] args) {
        int day = 3;

        String dayName = switch (day) {
            case 1 -> "Monday";
            case 2 -> "Tuesday";
            case 3 -> "Wednesday"; // 输出 "Wednesday"
            case 4 -> "Thursday";
            case 5 -> "Friday";
            case 6 -> "Saturday";
            case 7 -> "Sunday";
            default -> "Invalid day";
        };

        System.out.println("Day: " + dayName);
    }
}
```

#### 总结

`switch` 语句是 Java 中用于多分支条件判断的控制结构。它提供了一种更加清晰和结构化的方式来处理多个条件分支，相比 `if-else` 语句在处理大量分支时更具可读性和维护性。`switch` 语句支持多种数据类型（包括整数、字符串和枚举），并且在 Java 12 及以上版本中，`switch` 语句也支持返回值的用法。理解和掌握 `switch` 语句的用法可以帮助编写更简洁、逻辑更清晰的代码。

### Java 中的 `while` 语句

`while` 语句是 Java 中的一种循环控制结构，用于在满足特定条件时反复执行一段代码。与 `for` 循环相比，`while` 循环更适合在循环次数不确定的情况下使用。

#### 1. 基本语法

`while` 语句的基本语法如下：

```java
while (condition) {
    // code to be executed repeatedly as long as condition is true
}
```

- **condition**：这是一个布尔表达式，当其结果为 `true` 时，`while` 循环内部的代码块会重复执行；当其结果为 `false` 时，循环结束，程序继续执行循环后的代码。

**示例：**
```java
public class WhileExample {
    public static void main(String[] args) {
        int count = 1;

        while (count <= 5) {
            System.out.println("Count is: " + count); // 输出 "Count is: 1" 到 "Count is: 5"
            count++;
        }
    }
}
```

在这个示例中，循环会从 `count` 为 1 开始，随着每次迭代 `count` 加 1，当 `count` 变为 6 时，循环条件不再满足，循环结束。

#### 2. `while` 循环的注意事项

- **循环条件的更新**：在 `while` 循环中，必须确保循环条件能够在某个时刻变为 `false`，否则循环会无限执行，导致程序陷入死循环。例如，如果上面的例子中没有 `count++` 语句，`count` 会一直等于 1，循环条件始终为 `true`，导致死循环。

- **循环体可能不执行**：如果 `while` 循环的初始条件为 `false`，则循环体的代码不会执行一次。例如：

  ```java
  int count = 10;
  
  while (count < 5) {
      System.out.println("This will never be printed.");
  }
  ```
  在这个示例中，由于循环条件 `count < 5` 最初为 `false`，循环体的代码永远不会执行。

#### 3. 无限循环

在某些情况下，需要使用无限循环，通常与特定的 `break` 条件结合使用。`while(true)` 是创建无限循环的一种常见方式。

**示例：**
```java
public class InfiniteLoopExample {
    public static void main(String[] args) {
        while (true) {
            System.out.println("This loop will run forever.");
            // 可使用 break 语句在某些条件下退出循环
            break; // 此处添加 break 以退出循环
        }
    }
}
```

在这个示例中，如果没有 `break` 语句，`while (true)` 将导致无限循环，程序将一直输出 "This loop will run forever."。

#### 4. 使用 `break` 和 `continue`

- **`break` 语句**：`break` 语句可以用于立即退出循环，无论条件是否为 `true`。

  **示例：**
  ```java
  public class BreakExample {
      public static void main(String[] args) {
          int count = 1;

          while (count <= 10) {
              if (count == 5) {
                  break; // 当 count 等于 5 时，退出循环
              }
              System.out.println("Count is: " + count);
              count++;
          }
      }
  }
  ```

  在这个示例中，当 `count` 等于 5 时，循环会被 `break` 语句强制终止，输出会停止。

- **`continue` 语句**：`continue` 语句用于跳过当前循环的剩余部分，并立即开始下一次循环迭代。

  **示例：**
  ```java
  public class ContinueExample {
      public static void main(String[] args) {
          int count = 0;
  
          while (count < 10) {
              count++;
              if (count % 2 == 0) {
                  continue; // 如果 count 是偶数，跳过本次循环的剩余部分
              }
              System.out.println("Count is: " + count); // 只输出奇数
          }
      }
  }
  ```

  在这个示例中，`continue` 语句使得当 `count` 为偶数时，循环的剩余部分被跳过，因此只输出奇数值。

#### 5. 嵌套 `while` 循环

`while` 循环可以嵌套在另一个 `while` 循环中，这在处理多维数据或复杂逻辑时非常有用。

**示例：**
```java
public class NestedWhileExample {
    public static void main(String[] args) {
        int i = 1;

        while (i <= 3) {
            int j = 1;
            while (j <= 3) {
                System.out.println("i = " + i + ", j = " + j);
                j++;
            }
            i++;
        }
    }
}
```

在这个示例中，外层 `while` 循环控制变量 `i` 的值，内层 `while` 循环控制变量 `j` 的值，输出将显示 `i` 和 `j` 的组合。

#### 总结

`while` 语句是 Java 中一种重要的循环控制结构，适用于在不确定循环次数的情况下反复执行代码。掌握 `while` 循环的基本用法、无限循环、以及与 `break` 和 `continue` 结合的使用，可以帮助编写更加灵活和高效的循环代码。在编写 `while` 循环时，要特别注意循环条件的变化，以避免陷入死循环。

### Java 中的 `do-while` 语句

`do-while` 语句是 Java 中的一种循环控制结构，与 `while` 循环类似，但有一个关键区别：`do-while` 循环会先执行一次循环体内的代码，然后再判断条件是否满足。如果条件为 `true`，循环体会继续执行；如果条件为 `false`，循环结束。因此，`do-while` 循环至少执行一次循环体。

#### 1. 基本语法

`do-while` 语句的基本语法如下：

```java
do {
    // code to be executed
} while (condition);
```

- **code to be executed**：循环体内的代码块，无论条件如何，都会至少执行一次。
- **condition**：一个布尔表达式，当其结果为 `true` 时，循环会继续执行；当其结果为 `false` 时，循环终止。

**示例：**
```java
public class DoWhileExample {
    public static void main(String[] args) {
        int count = 1;

        do {
            System.out.println("Count is: " + count); // 输出 "Count is: 1" 到 "Count is: 5"
            count++;
        } while (count <= 5);
    }
}
```

在这个示例中，循环从 `count` 为 1 开始，由于 `do-while` 语句的结构，即使 `count` 最初就大于 5，循环体内的代码也会执行至少一次。

#### 2. `do-while` 与 `while` 的区别

- **执行顺序**：`while` 循环首先判断条件是否满足，然后决定是否执行循环体。如果条件一开始为 `false`，循环体一次也不会执行。而 `do-while` 循环则是先执行一次循环体，然后再判断条件是否继续执行循环。因此，即使条件一开始为 `false`，`do-while` 循环体也会执行一次。

  **示例（`while` 循环）：**
  ```java
  int count = 6;
  
  while (count <= 5) {
      System.out.println("This will not be printed because count is greater than 5.");
  }
  ```

  **示例（`do-while` 循环）：**
  ```java
  int count = 6;
  
  do {
      System.out.println("This will be printed once even though count is greater than 5.");
  } while (count <= 5);
  ```

  在 `while` 循环的示例中，由于条件一开始就不满足，循环体不会执行；而在 `do-while` 循环的示例中，尽管条件不满足，循环体仍会执行一次。

#### 3. 无限循环与 `do-while`

与 `while` 循环类似，`do-while` 也可以用于创建无限循环。

**示例：**
```java
public class DoWhileInfiniteLoop {
    public static void main(String[] args) {
        int count = 1;

        do {
            System.out.println("Infinite loop, count: " + count);
            count++;
            if (count == 10) break; // 为避免死循环，此处使用 break 退出循环
        } while (true);
    }
}
```

在这个示例中，`do-while` 循环会一直执行，直到通过 `break` 语句退出循环。

#### 4. 使用 `break` 和 `continue`

`do-while` 循环中同样可以使用 `break` 和 `continue` 语句来控制循环的执行流程。

- **`break` 语句**：立即退出循环。

  **示例：**
  ```java
  public class DoWhileBreakExample {
      public static void main(String[] args) {
          int count = 1;

          do {
              System.out.println("Count is: " + count);
              if (count == 3) {
                  break; // 当 count 等于 3 时，退出循环
              }
              count++;
          } while (count <= 5);
      }
  }
  ```

  在这个示例中，当 `count` 等于 3 时，循环会被 `break` 语句强制终止，不再继续。

- **`continue` 语句**：跳过当前循环的剩余部分，立即进行下一次循环迭代。

  **示例：**
  ```java
  public class DoWhileContinueExample {
      public static void main(String[] args) {
          int count = 0;
  
          do {
              count++;
              if (count % 2 == 0) {
                  continue; // 如果 count 是偶数，跳过本次循环的剩余部分
              }
              System.out.println("Count is: " + count); // 只输出奇数
          } while (count < 10);
      }
  }
  ```

  在这个示例中，`continue` 语句使得当 `count` 为偶数时，跳过当前循环的剩余部分，直接进入下一次循环，因此只输出奇数值。

#### 5. 嵌套 `do-while` 循环

`do-while` 循环可以嵌套在另一个 `do-while` 循环中，适用于处理多层次的循环逻辑。

**示例：**
```java
public class NestedDoWhileExample {
    public static void main(String[] args) {
        int i = 1;

        do {
            int j = 1;
            do {
                System.out.println("i = " + i + ", j = " + j);
                j++;
            } while (j <= 3);
            i++;
        } while (i <= 3);
    }
}
```

在这个示例中，外层 `do-while` 循环控制变量 `i` 的值，内层 `do-while` 循环控制变量 `j` 的值，输出将显示 `i` 和 `j` 的组合。

#### 总结

`do-while` 语句在 Java 中是一种特殊的循环结构，它确保循环体至少执行一次，然后根据条件决定是否继续循环。这种循环结构非常适合用于需要至少执行一次操作的场景。通过理解 `do-while` 的基本语法、`break` 和 `continue` 的使用、以及嵌套循环的应用，能够帮助你编写更加灵活和实用的循环代码。

### Java 中的 `for` 语句

`for` 语句是 Java 中的一种循环控制结构，用于在特定次数内反复执行一段代码。与 `while` 和 `do-while` 循环相比，`for` 循环通常用于需要知道循环次数的场景。

#### 1. 基本语法

`for` 循环的基本语法如下：

```java
for (initialization; condition; update) {
    // code to be executed repeatedly
}
```

- **initialization**：在循环开始前执行的初始化语句，通常用于声明和初始化控制变量。这部分只执行一次。
- **condition**：每次循环开始前都会检查这个条件。如果条件为 `true`，循环体执行；如果条件为 `false`，循环结束。
- **update**：在每次循环体执行完之后执行的语句，通常用于更新控制变量的值。

**示例：**
```java
public class ForLoopExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            System.out.println("i is: " + i); // 输出 "i is: 1" 到 "i is: 5"
        }
    }
}
```

在这个示例中，`for` 循环从 `i = 1` 开始，每次迭代后 `i` 增加 1。当 `i` 超过 5 时，循环结束。

#### 2. `for` 循环的执行流程

1. **初始化**：首先执行初始化语句，一般用于声明循环控制变量。此步骤只执行一次。
2. **条件判断**：检查条件表达式，如果结果为 `true`，则执行循环体代码。如果为 `false`，循环结束。
3. **执行循环体**：条件为 `true` 时，执行循环体中的代码。
4. **更新控制变量**：每次循环结束后，执行更新语句，通常用于修改控制变量。
5. **重复步骤 2 到 4**，直到条件表达式的结果为 `false`。

#### 3. `for` 循环的变体

- **省略部分组件**：`for` 循环的三个部分（初始化、条件、更新）都可以省略，但必须保留分号。如果省略条件部分，默认条件为 `true`，即无限循环。

  **示例：**
  ```java
  int i = 1;
  for (; i <= 5;) { // 省略了初始化和更新部分
      System.out.println("i is: " + i);
      i++;
  }
  ```

  这种写法与标准的 `while` 循环类似。

- **无限循环**：通过省略条件表达式，可以创建一个无限循环。

  **示例：**
  ```java
  for (;;) {
      System.out.println("This will print forever");
      // 添加条件以退出循环，避免死循环
      break; // 使用 break 语句跳出循环
  }
  ```

#### 4. `for-each` 循环

Java 提供了一种简化数组或集合遍历的 `for-each` 循环（也称为增强型 `for` 循环）。

**语法：**
```java
for (type element : array) {
    // code to be executed
}
```

- **type**：元素的类型。
- **element**：循环过程中每次迭代时从数组或集合中取出的元素。
- **array**：要遍历的数组或集合。

**示例：**
```java
public class ForEachExample {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        for (int number : numbers) {
            System.out.println("Number is: " + number); // 输出 "Number is: 1" 到 "Number is: 5"
        }
    }
}
```

`for-each` 循环非常适合遍历数组或集合，因为它简化了遍历操作，无需担心数组下标或集合的迭代器。

#### 5. 嵌套 `for` 循环

`for` 循环可以嵌套在另一个 `for` 循环中，适用于处理多维数组或复杂逻辑。

**示例：**
```java
public class NestedForExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 3; i++) {
            for (int j = 1; j <= 3; j++) {
                System.out.println("i = " + i + ", j = " + j);
            }
        }
    }
}
```

在这个示例中，外层 `for` 循环控制变量 `i` 的值，内层 `for` 循环控制变量 `j` 的值，输出将显示 `i` 和 `j` 的组合。

#### 6. 使用 `break` 和 `continue`

- **`break` 语句**：立即终止整个循环，跳出 `for` 语句块。

  **示例：**
  ```java
  public class BreakExample {
      public static void main(String[] args) {
          for (int i = 1; i <= 5; i++) {
              if (i == 3) {
                  break; // 当 i 等于 3 时，退出循环
              }
              System.out.println("i is: " + i);
          }
      }
  }
  ```

  在这个示例中，当 `i` 等于 3 时，循环被 `break` 语句强制终止，输出停止。

- **`continue` 语句**：跳过当前循环的剩余部分，立即开始下一次循环迭代。

  **示例：**
  ```java
  public class ContinueExample {
      public static void main(String[] args) {
          for (int i = 1; i <= 5; i++) {
              if (i == 3) {
                  continue; // 当 i 等于 3 时，跳过剩余部分
              }
              System.out.println("i is: " + i); // 不会打印 i = 3
          }
      }
  }
  ```

  在这个示例中，当 `i` 等于 3 时，`continue` 语句使得该次循环剩余部分被跳过，直接进入下一次循环，因此不会输出 `i = 3`。

#### 总结

`for` 语句是 Java 中最常用的循环控制结构之一，适用于已知循环次数的场景。`for-each` 循环进一步简化了对数组和集合的遍历操作。通过灵活运用 `for` 循环、`break` 和 `continue` 语句，以及嵌套循环，能够高效地处理复杂的循环逻辑。在使用 `for` 循环时，要确保循环条件正确，以避免无限循环或逻辑错误。

# Java数据结构

## 数组

### 普通数组

Java 中的数组是一种用于存储同一类型数据的容器。它们是固定长度的，数组元素的类型可以是基本数据类型或引用数据类型。数组通过索引来访问，从 0 开始计数。

#### 1. 数组的定义

在 Java 中，数组可以使用以下两种方式定义：

1. **声明数组变量**：
   ```java
   int[] arrayName;
   ```
   或者
   ```java
   int arrayName[];
   ```

   两种方式都是合法的，推荐使用第一种方式，因为它更清晰。

#### 2. 数组的初始化

数组的初始化可以在声明时同时进行，也可以在声明后进行。

- **在声明时初始化**：
  ```java
  int[] arrayName = new int[5]; // 创建一个包含 5 个整数的数组，所有元素初始值为 0
  ```

- **在声明后初始化**：
  ```java
  arrayName = new int[5];
  ```

- **直接赋值初始化**：
  ```java
  int[] arrayName = {1, 2, 3, 4, 5}; // 创建并初始化一个包含 5 个元素的数组
  ```

#### 3. 数组的赋值

数组中的元素可以通过索引进行访问和赋值。

**示例**：
```java
public class ArrayExample {
    public static void main(String[] args) {
        int[] numbers = new int[5]; // 创建一个包含 5 个整数的数组

        // 为数组中的每个元素赋值
        numbers[0] = 10;
        numbers[1] = 20;
        numbers[2] = 30;
        numbers[3] = 40;
        numbers[4] = 50;

        // 访问数组元素
        System.out.println("Element at index 0: " + numbers[0]);
        System.out.println("Element at index 1: " + numbers[1]);
    }
}
```

#### 4. 常见的数组操作

1. **获取数组长度**：
   使用 `length` 属性获取数组的长度。

   **示例**：
   ```java
   int length = numbers.length;
   System.out.println("Array length: " + length);
   ```

2. **访问和修改数组元素**：
   通过索引访问或修改数组中的元素。

   **示例**：
   ```java
   int firstElement = numbers[0]; // 访问第一个元素
   numbers[2] = 25; // 修改第三个元素的值为 25
   ```

3. **数组遍历**：
   使用 `for` 循环或 `for-each` 循环遍历数组。

   **使用 `for` 循环遍历**：
   ```java
   for (int i = 0; i < numbers.length; i++) {
       System.out.println("Element at index " + i + ": " + numbers[i]);
   }
   ```

   **使用 `for-each` 循环遍历**：
   ```java
   for (int number : numbers) {
       System.out.println("Element: " + number);
   }
   ```

4. **数组填充**：
   使用 `Arrays.fill` 方法填充数组的所有元素或部分元素。

   **示例**：
   ```java
   java.util.Arrays.fill(numbers, 10); // 将数组的所有元素填充为 10
   java.util.Arrays.fill(numbers, 1, 3, 20); // 将索引 1 到 2 的元素填充为 20
   ```

5. **数组排序**：
   使用 `Arrays.sort` 方法对数组进行排序。

   **示例**：
   ```java
   java.util.Arrays.sort(numbers);
   ```

6. **数组拷贝**：
   使用 `System.arraycopy` 或 `Arrays.copyOf` 方法进行数组的拷贝。

   **示例**：
   ```java
   int[] copy = new int[5];
   System.arraycopy(numbers, 0, copy, 0, numbers.length); // 复制数组
   ```

   或者使用：
   ```java
   int[] copy = java.util.Arrays.copyOf(numbers, numbers.length); // 复制数组
   ```

7. **数组搜索**：
   使用 `Arrays.binarySearch` 方法查找数组中的元素，前提是数组已排序。

   **示例**：
   ```java
   int index = java.util.Arrays.binarySearch(numbers, 30);
   if (index >= 0) {
       System.out.println("Element found at index: " + index);
   } else {
       System.out.println("Element not found");
   }
   ```

8. **数组反转**：
   Java 标准库没有直接提供数组反转的方法，但可以通过手动实现反转。

   **示例**：
   ```java
   public static void reverse(int[] array) {
       int n = array.length;
       for (int i = 0; i < n / 2; i++) {
           int temp = array[i];
           array[i] = array[n - 1 - i];
           array[n - 1 - i] = temp;
       }
   }
   
   public static void main(String[] args) {
       int[] numbers = {1, 2, 3, 4, 5};
       reverse(numbers);
       for (int number : numbers) {
           System.out.print(number + " "); // 输出 5 4 3 2 1
       }
   }
   ```

#### 5. 数组的注意事项

1. **索引越界**：
   访问或修改数组元素时，索引必须在合法范围内（0 到数组长度 - 1）。否则会抛出 `ArrayIndexOutOfBoundsException` 异常。

   **示例**：
   ```java
   numbers[5] = 60; // 抛出 ArrayIndexOutOfBoundsException 异常，因为数组长度为 5，索引最大为 4
   ```

2. **数组长度固定**：
   数组在创建时长度固定，不能动态改变。如果需要动态调整大小，建议使用 `ArrayList`。

3. **多维数组**：
   Java 支持多维数组（如二维数组、三维数组）。它们可以看作是数组的数组。

   **示例**：
   ```java
   int[][] matrix = new int[3][3]; // 创建一个 3x3 的二维数组
   matrix[0][0] = 1; // 访问二维数组的元素
   ```

4. **初始化默认值**：
   数组的元素在分配内存时会被自动初始化。对于整型数组，默认值是 0；对于浮点型数组，默认值是 0.0；对于布尔型数组，默认值是 `false`；对于引用类型数组，默认值是 `null`。

   **示例**：
   ```java
   boolean[] flags = new boolean[3]; // flags[0], flags[1], flags[2] 默认值为 false
   ```

5. **数组是对象**：
   在 Java 中，数组是对象。数组变量实际上是对内存中数组对象的引用。因此，数组变量可以在函数中传递并改变原数组内容。

   **示例**：
   ```java
   public static void modifyArray(int[] arr) {
       arr[0] = 100; // 修改数组的第一个元素
   }
   
   public static void main(String[] args) {
       int[] numbers = {1, 2, 3};
       modifyArray(numbers);
       System.out.println(numbers[0]); // 输出 100，说明原数组被修改
   }
   ```

#### 6. 总结

Java 中的数组是一种基本且重要的数据结构，用于存储相同类型的元素。它们的长度在创建时固定，不可改变。通过掌握数组的定义、初始化、赋值和常见操作（如遍历、排序、拷贝等），可以有效地管理和处理一组数据。需要注意的是，数组在使用时要确保索引在合法范围内，以避免越界异常。同时，由于数组是对象，通过引用传递时要注意可能的副作用。掌握数组的操作对于编写高效的 Java 程序至关重要。

### `ArrayList`

`ArrayList` 是 Java 集合框架中的一个动态数组类，位于 `java.util` 包中。与普通的数组不同，`ArrayList` 可以动态调整大小，允许添加或删除元素，而无需担心数组的固定长度。

#### 1. `ArrayList` 的定义

`ArrayList` 可以用以下方式进行定义：

```java
import java.util.ArrayList;

ArrayList<Type> arrayListName = new ArrayList<>();
```

- `Type` 是 `ArrayList` 中元素的类型，例如 `Integer`、`String` 等。
- `arrayListName` 是 `ArrayList` 对象的名称。

**示例**：
```java
ArrayList<String> names = new ArrayList<>();
```

#### 2. `ArrayList` 的初始化

`ArrayList` 在创建时可以通过构造函数指定初始容量（容量指的是`ArrayList` 可以容纳的元素数，而不是当前实际存储的元素数）。

**示例**：
```java
ArrayList<String> names = new ArrayList<>(10); // 初始化容量为10
```

也可以使用默认构造函数，默认初始容量为 10：
```java
ArrayList<String> names = new ArrayList<>();
```

#### 3. `ArrayList` 的赋值

`ArrayList` 可以使用 `add` 方法向其中添加元素。

**示例**：
```java
ArrayList<String> names = new ArrayList<>();
names.add("Alice");
names.add("Bob");
names.add("Charlie");
```

也可以在指定索引位置添加元素：
```java
names.add(1, "David"); // 在索引1位置添加 "David"，其他元素向后移位
```

#### 4. 常用的 `ArrayList` 方法

`ArrayList` 提供了许多操作集合的方法，以下是一些常用的方法及其详细说明：

1. **添加元素 (`add`)**：
   - `boolean add(E e)`：将指定的元素添加到列表的末尾。
   - `void add(int index, E element)`：在指定索引位置插入元素，后面的元素向后移动。

   **示例**：
   ```java
   ArrayList<String> names = new ArrayList<>();
   names.add("Alice");
   names.add(1, "Bob");
   ```

2. **获取元素 (`get`)**：
   - `E get(int index)`：返回列表中指定位置的元素。

   **示例**：
   ```java
   String name = names.get(0); // 获取索引0处的元素
   ```

3. **修改元素 (`set`)**：
   - `E set(int index, E element)`：将指定位置的元素替换为指定的元素。

   **示例**：
   ```java
   names.set(1, "David"); // 将索引1处的元素替换为 "David"
   ```

4. **删除元素 (`remove`)**：
   - `E remove(int index)`：删除指定位置的元素，返回被删除的元素。
   - `boolean remove(Object o)`：删除列表中第一个出现的指定元素，成功返回 `true`，否则返回 `false`。

   **示例**：
   ```java
   names.remove(1); // 删除索引1处的元素
   names.remove("Alice"); // 删除第一次出现的 "Alice"
   ```

5. **查找元素 (`indexOf`, `lastIndexOf`, `contains`)**：
   - `int indexOf(Object o)`：返回列表中第一次出现指定元素的索引，如果列表中不包含该元素，则返回 -1。
   - `int lastIndexOf(Object o)`：返回列表中最后一次出现指定元素的索引，如果列表中不包含该元素，则返回 -1。
   - `boolean contains(Object o)`：如果列表中包含指定的元素，则返回 `true`。

   **示例**：
   ```java
   int index = names.indexOf("Bob"); // 查找 "Bob" 的第一次出现位置
   boolean containsAlice = names.contains("Alice"); // 检查是否包含 "Alice"
   ```

6. **获取 `ArrayList` 的大小 (`size`)**：
   - `int size()`：返回列表中的元素数量。

   **示例**：
   ```java
   int size = names.size(); // 获取列表的大小
   ```

7. **清空列表 (`clear`)**：
   - `void clear()`：从列表中删除所有元素。

   **示例**：
   ```java
   names.clear(); // 清空列表
   ```

8. **判断列表是否为空 (`isEmpty`)**：
   - `boolean isEmpty()`：如果列表不包含元素，则返回 `true`。

   **示例**：
   ```java
   boolean isEmpty = names.isEmpty(); // 检查列表是否为空
   ```

9. **遍历列表**：
   - 可以使用 `for` 循环、增强的 `for` 循环、或使用 `Iterator` 进行遍历。

   **使用 `for` 循环**：
   ```java
   for (int i = 0; i < names.size(); i++) {
       System.out.println(names.get(i));
   }
   ```

   **使用增强的 `for` 循环**：
   ```java
   for (String name : names) {
       System.out.println(name);
   }
   ```

   **使用 `Iterator`**：
   ```java
   Iterator<String> iterator = names.iterator();
   while (iterator.hasNext()) {
       System.out.println(iterator.next());
   }
   ```

10. **转换为数组 (`toArray`)**：
    - `Object[] toArray()`：将列表中的所有元素转换为一个数组。
    - `<T> T[] toArray(T[] a)`：将列表中的元素转换为指定类型的数组。

    **示例**：
    ```java
    Object[] nameArray = names.toArray(); // 转换为 Object 数组
    String[] nameArray2 = names.toArray(new String[0]); // 转换为 String 数组
    ```

11. **排序 (`sort`)**：
    - `void sort(Comparator<? super E> c)`：使用指定的比较器对列表进行排序。

    **示例**：
    ```java
    names.sort(Comparator.naturalOrder()); // 按自然顺序排序
    ```

12. **替换所有元素 (`replaceAll`)**：
    - `void replaceAll(UnaryOperator<E> operator)`：用指定的操作替换列表中的所有元素。

    **示例**：
    ```java
    names.replaceAll(String::toUpperCase); // 将所有元素转换为大写
    ```

13. **过滤列表 (`removeIf`)**：
    - `boolean removeIf(Predicate<? super E> filter)`：删除符合指定条件的所有元素。

    **示例**：
    ```java
    names.removeIf(name -> name.startsWith("A")); // 删除以 "A" 开头的所有元素
    ```

14. **子列表 (`subList`)**：
    - `List<E> subList(int fromIndex, int toIndex)`：返回从 `fromIndex`（包括）到 `toIndex`（不包括）之间的元素组成的子列表。

    **示例**：
    ```java
    List<String> subList = names.subList(1, 3); // 获取索引1到2的子列表
    ```

#### 5. 总结

`ArrayList` 是 Java 中一个非常灵活和强大的集合类。它允许动态调整大小，提供了丰富的方法用于添加、删除、修改和查询元素。与数组相比，`ArrayList` 更适合用于需要频繁添加或删除元素的场景。通过理解和使用 `ArrayList` 提供的各种方法，可以有效地管理和操作动态集合中的数据。在性能方面，`ArrayList` 提供了较高的访问速度，但在频繁插入或删除操作时，可能会因为数组的动态扩展和移动元素而导致性能下降。在实际应用中，选择 `ArrayList` 还是数组需要根据具体的需求来决定。

### `LinkedList` 

`LinkedList` 是 Java 集合框架中的一个双向链表实现，位于 `java.util` 包中。与 `ArrayList` 不同，`LinkedList` 使用链表数据结构来存储元素，可以高效地进行插入和删除操作。

#### 1. `LinkedList` 的定义

`LinkedList` 可以用以下方式进行定义：

```java
import java.util.LinkedList;

LinkedList<Type> linkedListName = new LinkedList<>();
```

- `Type` 是 `LinkedList` 中元素的类型，例如 `Integer`、`String` 等。
- `linkedListName` 是 `LinkedList` 对象的名称。

**示例**：
```java
LinkedList<String> names = new LinkedList<>();
```

#### 2. `LinkedList` 的初始化

`LinkedList` 在创建时无需指定容量，因为它基于链表结构，大小可以动态增长。

**示例**：
```java
LinkedList<String> names = new LinkedList<>();
```

#### 3. `LinkedList` 的赋值

`LinkedList` 可以使用 `add` 方法向其中添加元素。

**示例**：
```java
LinkedList<String> names = new LinkedList<>();
names.add("Alice");
names.add("Bob");
names.add("Charlie");
```

也可以在指定索引位置添加元素：
```java
names.add(1, "David"); // 在索引1位置添加 "David"
```

#### 4. 常用的 `LinkedList` 方法

`LinkedList` 提供了多种方法来操作链表，包括添加、删除、查看元素等。以下是一些常用的方法及其详细说明：

1. **添加元素 (`add`)**：
   - `boolean add(E e)`：将指定的元素添加到列表的末尾。
   - `void add(int index, E element)`：在指定索引位置插入元素。
   - `void addFirst(E e)`：将指定的元素插入到列表的开头。
   - `void addLast(E e)`：将指定的元素添加到列表的末尾。

   **示例**：
   ```java
   LinkedList<String> names = new LinkedList<>();
   names.add("Alice");
   names.add(1, "Bob");
   names.addFirst("Charlie");
   names.addLast("David");
   ```

2. **获取元素 (`get`)**：
   - `E get(int index)`：返回列表中指定位置的元素。
   - `E getFirst()`：返回列表中的第一个元素。
   - `E getLast()`：返回列表中的最后一个元素。

   **示例**：
   ```java
   String first = names.getFirst(); // 获取第一个元素
   String last = names.getLast(); // 获取最后一个元素
   ```

3. **修改元素 (`set`)**：
   - `E set(int index, E element)`：将指定位置的元素替换为指定的元素。

   **示例**：
   ```java
   names.set(1, "David"); // 将索引1处的元素替换为 "David"
   ```

4. **删除元素 (`remove`)**：
   - `E remove(int index)`：删除指定位置的元素，返回被删除的元素。
   - `boolean remove(Object o)`：删除列表中第一次出现的指定元素，成功返回 `true`。
   - `E removeFirst()`：删除并返回列表中的第一个元素。
   - `E removeLast()`：删除并返回列表中的最后一个元素。

   **示例**：
   ```java
   names.remove(1); // 删除索引1处的元素
   names.remove("Alice"); // 删除第一次出现的 "Alice"
   names.removeFirst(); // 删除第一个元素
   names.removeLast(); // 删除最后一个元素
   ```

5. **检查元素 (`contains`, `indexOf`, `lastIndexOf`)**：
   - `boolean contains(Object o)`：如果列表中包含指定的元素，则返回 `true`。
   - `int indexOf(Object o)`：返回列表中第一次出现指定元素的索引，如果列表中不包含该元素，则返回 -1。
   - `int lastIndexOf(Object o)`：返回列表中最后一次出现指定元素的索引，如果列表中不包含该元素，则返回 -1。

   **示例**：
   ```java
   boolean containsAlice = names.contains("Alice"); // 检查是否包含 "Alice"
   int index = names.indexOf("Bob"); // 查找 "Bob" 的第一次出现位置
   ```

6. **获取 `LinkedList` 的大小 (`size`)**：
   - `int size()`：返回列表中的元素数量。

   **示例**：
   ```java
   int size = names.size(); // 获取列表的大小
   ```

7. **清空列表 (`clear`)**：
   - `void clear()`：从列表中删除所有元素。

   **示例**：
   ```java
   names.clear(); // 清空列表
   ```

8. **判断列表是否为空 (`isEmpty`)**：
   - `boolean isEmpty()`：如果列表不包含元素，则返回 `true`。

   **示例**：
   ```java
   boolean isEmpty = names.isEmpty(); // 检查列表是否为空
   ```

9. **遍历列表**：
   - 可以使用 `for` 循环、增强的 `for` 循环、或使用 `Iterator` 进行遍历。

   **使用 `for` 循环**：
   ```java
   for (int i = 0; i < names.size(); i++) {
       System.out.println(names.get(i));
   }
   ```

   **使用增强的 `for` 循环**：
   ```java
   for (String name : names) {
       System.out.println(name);
   }
   ```

   **使用 `Iterator`**：
   ```java
   Iterator<String> iterator = names.iterator();
   while (iterator.hasNext()) {
       System.out.println(iterator.next());
   }
   ```

10. **转换为数组 (`toArray`)**：
    - `Object[] toArray()`：将列表中的所有元素转换为一个数组。
    - `<T> T[] toArray(T[] a)`：将列表中的元素转换为指定类型的数组。

    **示例**：
    ```java
    Object[] nameArray = names.toArray(); // 转换为 Object 数组
    String[] nameArray2 = names.toArray(new String[0]); // 转换为 String 数组
    ```

11. **队列操作 (`offer`, `poll`, `peek`)**：
    - `boolean offer(E e)`：将元素添加到列表的末尾，相当于 `addLast`。
    - `E poll()`：检索并移除列表的头元素，返回该元素；如果列表为空，则返回 `null`。
    - `E peek()`：检索但不移除列表的头元素，如果列表为空，则返回 `null`。

    **示例**：
    ```java
    names.offer("Eve"); // 将元素添加到队列的末尾
    String head = names.poll(); // 获取并移除队列头元素
    String headPeek = names.peek(); // 获取但不移除队列头元素
    ```

12. **栈操作 (`push`, `pop`, `peek`)**：
    - `void push(E e)`：将元素推入栈顶（列表的头部）。
    - `E pop()`：移除并返回栈顶元素（列表的头部）。
    - `E peek()`：查看但不移除栈顶元素。

    **示例**：
    ```java
    names.push("Frank"); // 推入栈顶元素
    String top = names.pop(); // 移除并返回栈顶元素
    String topPeek = names.peek(); // 查看但不移除栈顶元素
    ```

#### 5. 总结

`LinkedList` 是 Java 集合框架中一个灵活的双向链表实现，适合频繁插入和删除元素的场景。与 `ArrayList` 相比，`LinkedList` 在这些操作上通常性能更好，因为它不需要像 `ArrayList` 那样移动大量元素。然而，`LinkedList` 的随机访问速度比 `ArrayList` 慢，因此在需要频繁访问元素的场景中，`ArrayList` 可能更为合适。了解 `LinkedList` 的特性及其常用操作，可以帮助你在编写程序时选择合适的数据结构。

## 栈

### `Stack` 

`Stack` 类是 Java 集合框架中的一个经典数据结构，用于表示一个后进先出（LIFO, Last In First Out）集合。它是 `java.util` 包的一部分，继承自 `Vector` 类，因此具有动态数组的特性。

#### 1. `Stack` 的定义

`Stack` 类可以使用以下方式进行定义：

```java
import java.util.Stack;

Stack<Type> stackName = new Stack<>();
```

- `Type` 是栈中元素的类型，例如 `Integer`、`String` 等。
- `stackName` 是 `Stack` 对象的名称。

**示例**：
```java
Stack<String> stack = new Stack<>();
```

#### 2. `Stack` 的基本操作

`Stack` 提供了多种方法来操作栈，包括添加、删除、查看元素等。

1. **入栈 (`push`)**：
   - `E push(E item)`：将指定的元素压入栈中。

   **示例**：
   ```java
   stack.push("Element1");
   stack.push("Element2");
   ```

2. **出栈 (`pop`)**：
   - `E pop()`：移除栈顶的元素并返回它。如果栈为空，会抛出 `EmptyStackException`。

   **示例**：
   ```java
   String topElement = stack.pop(); // 移除并返回栈顶元素
   ```

3. **查看栈顶元素 (`peek`)**：
   - `E peek()`：返回栈顶的元素但不移除它。如果栈为空，会抛出 `EmptyStackException`。

   **示例**：
   ```java
   String topElement = stack.peek(); // 返回栈顶元素但不移除
   ```

4. **检查栈是否为空 (`empty`)**：
   - `boolean empty()`：检查栈是否为空。如果栈为空，返回 `true`，否则返回 `false`。

   **示例**：
   ```java
   boolean isEmpty = stack.empty(); // 检查栈是否为空
   ```

5. **获取栈的大小 (`size`)**：
   - `int size()`：返回栈中元素的数量。

   **示例**：
   ```java
   int size = stack.size(); // 获取栈的大小
   ```

6. **查找元素位置 (`search`)**：
   - `int search(Object o)`：返回对象在栈中的位置（从栈顶开始计算），如果不存在返回 -1。

   **示例**：
   ```java
   int position = stack.search("Element1"); // 查找 "Element1" 的位置
   ```

#### 3. `Stack` 的注意事项

1. **继承自 `Vector`**：
   - `Stack` 是 `Vector` 的一个子类，继承了 `Vector` 的所有方法，例如 `add`, `remove`, `get` 等。因此，`Stack` 可以作为 `Vector` 的一种特化使用，但通常推荐使用栈特有的方法（如 `push`, `pop`）进行操作。

2. **线程安全**：
   - 由于 `Stack` 是 `Vector` 的子类，因此它是线程安全的。如果在多线程环境中使用栈，默认情况下不会出现线程安全问题。然而，如果不需要线程安全，可以考虑使用 `ArrayDeque` 来替代 `Stack`，它在单线程环境中通常性能更佳。

3. **性能考虑**：
   - `Stack` 类的性能在大多数情况下足够好，但它的性能不如 `ArrayDeque`。如果频繁进行栈操作，并且不需要线程安全，可以考虑使用 `ArrayDeque` 类来提高性能。

#### 4. 示例代码

下面是一个使用 `Stack` 类的简单示例，展示了如何进行基本的栈操作：

```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<String> stack = new Stack<>();

        // 入栈
        stack.push("First");
        stack.push("Second");
        stack.push("Third");

        // 查看栈顶元素
        System.out.println("Top element: " + stack.peek());

        // 出栈
        System.out.println("Popped element: " + stack.pop());
        System.out.println("Popped element: " + stack.pop());

        // 检查栈是否为空
        System.out.println("Is stack empty? " + stack.empty());

        // 查看栈的大小
        System.out.println("Stack size: " + stack.size());

        // 查找元素位置
        System.out.println("Position of 'First': " + stack.search("First"));
    }
}
```

#### 5. 总结

`Stack` 是一种非常有用的数据结构，适合处理需要后进先出逻辑的问题。它提供了一些基本操作，如入栈、出栈、查看栈顶元素等，并且由于继承自 `Vector`，它具备了线程安全的特性。然而，`Stack` 的性能在某些场景下可能不如 `ArrayDeque`，所以在性能敏感的应用中可以考虑使用其他实现。理解 `Stack` 的基本操作和特性，将帮助你在编程中有效地解决许多常见的问题。

## 队列

### Java 中的 `ArrayDeque` 类

`ArrayDeque` 是 Java 集合框架中的一个双端队列实现，位于 `java.util` 包中。`Deque` 代表双端队列（Double-Ended Queue），意味着元素可以从队列的两端进行插入和删除操作。`ArrayDeque` 是 `Deque` 接口的一个实现，它是基于数组的，且没有容量限制（自动扩展）。

#### 1. `ArrayDeque` 的定义

`ArrayDeque` 可以通过以下方式进行定义：

```java
import java.util.ArrayDeque;

ArrayDeque<Type> dequeName = new ArrayDeque<>();
```

- `Type` 是 `ArrayDeque` 中元素的类型，例如 `Integer`、`String` 等。
- `dequeName` 是 `ArrayDeque` 对象的名称。

**示例**：
```java
ArrayDeque<String> deque = new ArrayDeque<>();
```

#### 2. `ArrayDeque` 的初始化

`ArrayDeque` 在创建时可以选择指定初始容量，但也可以不指定，默认会有一个初始容量，当容量不足时会自动扩展。

**示例**：
```java
ArrayDeque<Integer> deque = new ArrayDeque<>(10); // 创建一个初始容量为10的ArrayDeque
```

#### 3. 常用的 `ArrayDeque` 方法

`ArrayDeque` 提供了丰富的方法来操作队列中的元素，包括添加、删除、查看元素等。以下是一些常用的方法及其详细说明：

1. **添加元素**：
   - `boolean add(E e)`：将指定的元素添加到队列的末尾，如果成功返回 `true`，如果队列已满抛出异常。
   - `void addFirst(E e)`：将指定的元素添加到队列的开头。
   - `void addLast(E e)`：将指定的元素添加到队列的末尾。
   - `boolean offer(E e)`：将指定的元素插入到队列的末尾，如果插入成功返回 `true`。
   - `boolean offerFirst(E e)`：将指定的元素插入到队列的开头。
   - `boolean offerLast(E e)`：将指定的元素插入到队列的末尾。

   **示例**：
   ```java
   deque.add("Alice");
   deque.addFirst("Bob");
   deque.addLast("Charlie");
   deque.offer("David");
   deque.offerFirst("Eve");
   deque.offerLast("Frank");
   ```

2. **删除元素**：
   - `E remove()`：删除并返回队列的头元素，如果队列为空，抛出异常。
   - `E removeFirst()`：删除并返回队列的第一个元素，如果队列为空，抛出异常。
   - `E removeLast()`：删除并返回队列的最后一个元素，如果队列为空，抛出异常。
   - `E poll()`：删除并返回队列的头元素，如果队列为空，返回 `null`。
   - `E pollFirst()`：删除并返回队列的第一个元素，如果队列为空，返回 `null`。
   - `E pollLast()`：删除并返回队列的最后一个元素，如果队列为空，返回 `null`。

   **示例**：
   ```java
   String head = deque.remove(); // 删除并返回头元素
   String first = deque.removeFirst(); // 删除并返回第一个元素
   String last = deque.removeLast(); // 删除并返回最后一个元素
   ```

3. **查看元素**：
   - `E getFirst()`：返回队列的第一个元素但不删除它，如果队列为空，抛出异常。
   - `E getLast()`：返回队列的最后一个元素但不删除它，如果队列为空，抛出异常。
   - `E peek()`：返回队列的头元素但不删除它，如果队列为空，返回 `null`。
   - `E peekFirst()`：返回队列的第一个元素但不删除它，如果队列为空，返回 `null`。
   - `E peekLast()`：返回队列的最后一个元素但不删除它，如果队列为空，返回 `null`。

   **示例**：
   ```java
   String first = deque.getFirst(); // 查看第一个元素
   String last = deque.getLast(); // 查看最后一个元素
   String head = deque.peek(); // 查看但不移除头元素
   ```

4. **栈操作**：
   - `void push(E e)`：将元素推入栈顶（队列的开头）。
   - `E pop()`：移除并返回栈顶元素（队列的开头）。

   **示例**：
   ```java
   deque.push("George"); // 推入栈顶元素
   String top = deque.pop(); // 移除并返回栈顶元素
   ```

5. **检查队列是否为空**：
   - `boolean isEmpty()`：如果队列为空，返回 `true`，否则返回 `false`。

   **示例**：
   ```java
   boolean isEmpty = deque.isEmpty(); // 检查队列是否为空
   ```

6. **获取队列的大小**：
   - `int size()`：返回队列中元素的数量。

   **示例**：
   ```java
   int size = deque.size(); // 获取队列的大小
   ```

7. **遍历 `ArrayDeque`**：
   - 可以使用 `for` 循环、增强的 `for` 循环或 `Iterator` 进行遍历。

   **使用 `for` 循环**：
   ```java
   for (int i = 0; i < deque.size(); i++) {
       System.out.println(deque.toArray()[i]);
   }
   ```

   **使用增强的 `for` 循环**：
   ```java
   for (String name : deque) {
       System.out.println(name);
   }
   ```

   **使用 `Iterator`**：
   ```java
   Iterator<String> iterator = deque.iterator();
   while (iterator.hasNext()) {
       System.out.println(iterator.next());
   }
   ```

8. **清空队列**：
   - `void clear()`：从队列中删除所有元素。

   **示例**：
   ```java
   deque.clear(); // 清空队列
   ```

#### 4. `ArrayDeque` 的优点和注意事项

1. **高效的双端操作**：
   - `ArrayDeque` 的设计非常高效，可以在队列的两端快速地进行插入和删除操作，适合实现栈、队列、双端队列等数据结构。

2. **无容量限制**：
   - `ArrayDeque` 是动态扩展的，没有预设的容量限制，因此它能够根据需要自动扩展，但与链表相比，内存利用率更高。

3. **不支持 `null` 元素**：
   - `ArrayDeque` 不允许存储 `null` 元素，试图添加 `null` 元素会抛出 `NullPointerException`。

4. **非线程安全**：
   - `ArrayDeque` 不是线程安全的。如果需要在多线程环境中使用 `ArrayDeque`，需要自行同步。

5. **比 `LinkedList` 更高效**：
   - 与 `LinkedList` 相比，`ArrayDeque` 在实现双端队列的同时具有更高的性能，特别是在涉及到大量插入和删除操作时。

#### 5. 示例代码

下面是一个简单的 `ArrayDeque` 示例，展示了如何使用双端队列的基本操作：

```java
import java.util.ArrayDeque;

public class ArrayDequeExample {
    public static void main(String[] args) {
        ArrayDeque<String> deque = new ArrayDeque<>();

        // 添加元素
        deque.add("Alice");
        deque.addFirst("Bob");
        deque.addLast("Charlie");

        // 查看元素
        System.out.println("First Element: " + deque.getFirst());
        System.out.println("Last Element: " + deque.getLast());

        // 删除元素
        System.out.println("Removed First Element: " + deque.removeFirst());
        System.out.println("Removed Last Element: " + deque.removeLast());

        // 栈操作
        deque.push("David");
        System.out.println("Popped Element: " + deque.pop());

        // 遍历
        deque.add("Eve");
        deque.add("Frank");

        for (String name : deque) {
            System.out.println(name);
        }
    }
}
```

#### 6. 总结

`ArrayDeque` 是一个灵活且高效的双端队列实现，适用于需要频繁从两端进行插入和删除操作的场景。它结合了栈、队列、双端队列的优势，并且在性能和内存利用率方面通常优于 `LinkedList`。理解和掌握 `ArrayDeque` 的使用，可以帮助你在编写高效程序时选择合适的数据结构。

## 集合

###  `HashSet` 

`HashSet` 是 Java 集合框架中的一个类，位于 `java.util` 包中。它实现了 `Set` 接口，表示一个不包含重复元素的集合。`HashSet` 是基于哈希表实现的，因此，它具有良好的查找、插入和删除性能，通常为 O(1) 时间复杂度。

#### 1. `HashSet` 的定义

`HashSet` 可以通过以下方式进行定义：

```java
import java.util.HashSet;

HashSet<Type> setName = new HashSet<>();
```

- `Type` 是 `HashSet` 中元素的类型，例如 `Integer`、`String` 等。
- `setName` 是 `HashSet` 对象的名称。

**示例**：
```java
HashSet<String> set = new HashSet<>();
```

#### 2. `HashSet` 的初始化

`HashSet` 可以通过无参构造器创建，也可以指定初始容量和加载因子。

- **默认构造方法**：创建一个默认容量为16，加载因子为0.75的 `HashSet`。
- **指定初始容量**：创建具有指定初始容量的 `HashSet`。
- **指定初始容量和加载因子**：创建具有指定初始容量和加载因子的 `HashSet`。

**示例**：
```java
HashSet<Integer> set1 = new HashSet<>(); // 默认容量和加载因子
HashSet<Integer> set2 = new HashSet<>(50); // 初始容量为50
HashSet<Integer> set3 = new HashSet<>(50, 0.5f); // 初始容量为50，加载因子为0.5
```

#### 3. `HashSet` 的常用方法

`HashSet` 提供了多种方法来操作集合中的元素，包括添加、删除、查看等。以下是一些常用的方法及其详细说明：

1. **添加元素**：
   - `boolean add(E e)`：将指定的元素添加到集合中，如果集合中已存在该元素，则返回 `false`，否则返回 `true`。

   **示例**：
   ```java
   set.add("Alice");
   set.add("Bob");
   ```

2. **删除元素**：
   - `boolean remove(Object o)`：从集合中删除指定的元素，如果元素存在于集合中且成功删除，则返回 `true`，否则返回 `false`。
   - `void clear()`：从集合中删除所有元素。

   **示例**：
   ```java
   set.remove("Alice"); // 删除元素 "Alice"
   set.clear(); // 清空集合
   ```

3. **检查元素**：
   - `boolean contains(Object o)`：如果集合中包含指定的元素，则返回 `true`，否则返回 `false`。

   **示例**：
   ```java
   boolean hasAlice = set.contains("Alice"); // 检查集合中是否包含 "Alice"
   ```

4. **获取集合的大小**：
   - `int size()`：返回集合中元素的数量。

   **示例**：
   ```java
   int size = set.size(); // 获取集合的大小
   ```

5. **检查集合是否为空**：
   - `boolean isEmpty()`：如果集合为空，则返回 `true`，否则返回 `false`。

   **示例**：
   ```java
   boolean isEmpty = set.isEmpty(); // 检查集合是否为空
   ```

6. **遍历 `HashSet`**：
   - 可以使用增强的 `for` 循环或 `Iterator` 进行遍历。

   **使用增强的 `for` 循环**：
   ```java
   for (String name : set) {
       System.out.println(name);
   }
   ```

   **使用 `Iterator`**：
   ```java
   Iterator<String> iterator = set.iterator();
   while (iterator.hasNext()) {
       System.out.println(iterator.next());
   }
   ```

7. **集合操作**：
   - `boolean addAll(Collection<? extends E> c)`：将指定集合中的所有元素添加到此集合中。
   - `boolean removeAll(Collection<?> c)`：从此集合中移除指定集合中包含的所有元素。
   - `boolean retainAll(Collection<?> c)`：仅保留此集合中指定集合中也包含的元素。

   **示例**：
   ```java
   HashSet<String> otherSet = new HashSet<>();
   otherSet.add("Charlie");
   otherSet.add("Dave");
   
   set.addAll(otherSet); // 将otherSet的元素添加到set中
   ```

#### 4. `HashSet` 的特点和注意事项

1. **不保证顺序**：
   - `HashSet` 中的元素没有特定的顺序，顺序可能会随着元素的添加或删除而变化。如果需要保持元素的插入顺序，可以使用 `LinkedHashSet`。

2. **不允许重复元素**：
   - `HashSet` 不允许存储重复的元素。如果尝试将一个已经存在于集合中的元素再次添加到集合中，`add` 方法将返回 `false`。

3. **允许存储 `null` 值**：
   - `HashSet` 允许存储一个 `null` 元素，但只能存储一个，因为 `null` 也被视为一个元素。

4. **线程不安全**：
   - `HashSet` 不是线程安全的。如果多个线程同时访问一个 `HashSet`，并且至少有一个线程修改了集合，那么它必须手动同步。如果需要线程安全的 `Set`，可以使用 `Collections.synchronizedSet` 方法来包装 `HashSet`。

5. **性能**：
   - `HashSet` 提供了常数时间的基本操作（`add`、`remove`、`contains` 和 `size`），但其性能取决于哈希函数的质量。

6. **加载因子和初始容量**：
   - 加载因子决定了在哈希表何时增长。较低的加载因子减少了冲突但增加了空间的使用，较高的加载因子节省了空间但增加了冲突。

#### 5. 示例代码

下面是一个简单的 `HashSet` 示例，展示了如何使用 `HashSet` 的基本操作：

```java
import java.util.HashSet;

public class HashSetExample {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();

        // 添加元素
        set.add("Alice");
        set.add("Bob");
        set.add("Charlie");

        // 检查元素
        System.out.println("Set contains 'Alice': " + set.contains("Alice"));
        System.out.println("Set contains 'David': " + set.contains("David"));

        // 遍历集合
        System.out.println("Elements in the set:");
        for (String name : set) {
            System.out.println(name);
        }

        // 删除元素
        set.remove("Alice");
        System.out.println("Set after removing 'Alice': " + set);

        // 获取集合大小
        System.out.println("Set size: " + set.size());

        // 清空集合
        set.clear();
        System.out.println("Set after clearing: " + set);
    }
}
```

#### 6. 总结

`HashSet` 是一个简单但功能强大的集合实现，适用于不需要重复元素且不关心元素顺序的场景。它在执行查找、插入和删除操作时表现出色，非常适合用于快速检查元素是否存在或去重的任务。理解和掌握 `HashSet` 的使用，可以帮助你在编写高效程序时选择合适的数据结构。

###  `HashMap` 

`HashMap` 是 Java 集合框架中的一个类，位于 `java.util` 包中。它是基于哈希表实现的 `Map` 接口的实现类，存储键值对（key-value pair）。`HashMap` 允许 `null` 键和 `null` 值，但不保证映射中的顺序。

#### 1. `HashMap` 的定义

`HashMap` 可以通过以下方式进行定义：

```java
import java.util.HashMap;

HashMap<KeyType, ValueType> mapName = new HashMap<>();
```

- `KeyType` 是键的类型，例如 `Integer`、`String` 等。
- `ValueType` 是值的类型。
- `mapName` 是 `HashMap` 对象的名称。

**示例**：
```java
HashMap<String, Integer> map = new HashMap<>();
```

#### 2. `HashMap` 的初始化

`HashMap` 可以通过无参构造器创建，也可以指定初始容量和加载因子。

- **默认构造方法**：创建一个默认初始容量为16，加载因子为0.75的 `HashMap`。
- **指定初始容量**：创建具有指定初始容量的 `HashMap`。
- **指定初始容量和加载因子**：创建具有指定初始容量和加载因子的 `HashMap`。

**示例**：
```java
HashMap<String, Integer> map1 = new HashMap<>(); // 默认容量和加载因子
HashMap<String, Integer> map2 = new HashMap<>(50); // 初始容量为50
HashMap<String, Integer> map3 = new HashMap<>(50, 0.5f); // 初始容量为50，加载因子为0.5
```

#### 3. `HashMap` 的常用方法

`HashMap` 提供了多种方法来操作映射中的键值对，包括添加、删除、查看等。以下是一些常用的方法及其详细说明：

1. **添加键值对**：
   - `V put(K key, V value)`：将指定的键和值插入到映射中。如果键已经存在，则更新其对应的值，并返回旧值；否则返回 `null`。

   **示例**：
   ```java
   map.put("Alice", 25);
   map.put("Bob", 30);
   ```

2. **获取值**：
   - `V get(Object key)`：返回与指定键对应的值。如果映射中不包含该键，返回 `null`。

   **示例**：
   ```java
   int age = map.get("Alice"); // 获取键 "Alice" 对应的值
   ```

3. **删除键值对**：
   - `V remove(Object key)`：如果存在指定的键，则将其对应的键值对从映射中移除，并返回该键的值；否则返回 `null`。
   - `void clear()`：从映射中移除所有键值对。

   **示例**：
   ```java
   map.remove("Alice"); // 删除键 "Alice" 对应的键值对
   map.clear(); // 清空映射
   ```

4. **检查键或值是否存在**：
   - `boolean containsKey(Object key)`：如果映射中包含指定的键，则返回 `true`，否则返回 `false`。
   - `boolean containsValue(Object value)`：如果映射中包含指定的值，则返回 `true`，否则返回 `false`。

   **示例**：
   ```java
   boolean hasAlice = map.containsKey("Alice"); // 检查是否包含键 "Alice"
   boolean hasAge30 = map.containsValue(30); // 检查是否包含值 30
   ```

5. **获取映射的大小**：
   - `int size()`：返回映射中键值对的数量。

   **示例**：
   ```java
   int size = map.size(); // 获取映射的大小
   ```

6. **检查映射是否为空**：
   - `boolean isEmpty()`：如果映射为空，则返回 `true`，否则返回 `false`。

   **示例**：
   ```java
   boolean isEmpty = map.isEmpty(); // 检查映射是否为空
   ```

7. **遍历 `HashMap`**：
   - 可以使用 `for-each` 循环或 `Iterator` 遍历 `HashMap`。

   **遍历键集**：
   ```java
   for (String key : map.keySet()) {
       System.out.println("Key: " + key);
   }
   ```

   **遍历值集**：
   ```java
   for (Integer value : map.values()) {
       System.out.println("Value: " + value);
   }
   ```

   **遍历键值对**：
   ```java
   for (Map.Entry<String, Integer> entry : map.entrySet()) {
       System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());
   }
   ```

8. **其他方法**：
   - `V putIfAbsent(K key, V value)`：如果指定的键不存在，则将该键值对插入到映射中。
   - `V getOrDefault(Object key, V defaultValue)`：返回与指定键对应的值，如果键不存在，则返回默认值 `defaultValue`。

   **示例**：
   ```java
   map.putIfAbsent("Charlie", 35); // 只有在键 "Charlie" 不存在时才插入
   int age = map.getOrDefault("David", 40); // 如果键 "David" 不存在，则返回 40
   ```

#### 4. `HashMap` 的特点和注意事项

1. **不保证顺序**：
   - `HashMap` 不保证键值对的顺序，顺序可能会随着元素的添加或删除而变化。如果需要保持插入顺序，可以使用 `LinkedHashMap`。

2. **允许 `null` 键和值**：
   - `HashMap` 允许一个 `null` 键和多个 `null` 值。通常，`null` 键用作特殊值，但应谨慎使用。

3. **线程不安全**：
   - `HashMap` 不是线程安全的。如果多个线程同时访问一个 `HashMap` 并且至少有一个线程修改了映射，则必须手动同步。如果需要线程安全的 `Map`，可以使用 `Collections.synchronizedMap` 方法来包装 `HashMap`。

4. **性能**：
   - `HashMap` 提供了常数时间的基本操作（`put`、`get`、`remove` 和 `containsKey`），但其性能取决于哈希函数的质量。

5. **加载因子和初始容量**：
   - 加载因子决定了哈希表何时扩展。较低的加载因子减少了冲突但增加了空间的使用，而较高的加载因子节省了空间但增加了冲突。

#### 5. 示例代码

下面是一个简单的 `HashMap` 示例，展示了如何使用 `HashMap` 的基本操作：

```java
import java.util.HashMap;
import java.util.Map;

public class HashMapExample {
    public static void main(String[] args) {
        HashMap<String, Integer> map = new HashMap<>();

        // 添加键值对
        map.put("Alice", 25);
        map.put("Bob", 30);
        map.put("Charlie", 35);

        // 获取值
        System.out.println("Alice's age: " + map.get("Alice"));

        // 检查键或值是否存在
        System.out.println("Contains key 'David': " + map.containsKey("David"));
        System.out.println("Contains value 30: " + map.containsValue(30));

        // 遍历映射
        System.out.println("All key-value pairs:");
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());
        }

        // 删除键值对
        map.remove("Alice");
        System.out.println("Map after removing 'Alice': " + map);

        // 获取映射大小
        System.out.println("Map size: " + map.size());

        // 清空映射
        map.clear();
        System.out.println("Map after clearing: " + map);
    }
}
```

#### 6. 总结

`HashMap` 是一个强大且灵活的映射实现，适用于需要快速查找、插入和删除键值对的场景。它支持 `null` 键和值，并且具有良好的性能，但在使用时需要注意线程安全和可能的哈希冲突。通过理解和掌握 `HashMap` 的使用，可以帮助你在处理键值对数据时选择合适的数据结构。

# 面向对象编程

## 面向对象编程基础

### 面向对象特征

> 类是封装对象的属性和行为的载体

面向对象的特点：

- 封装：即隐藏对象的属性和实现细节，仅对外公开接口，控制在程序中属性的读和修改的访问级别。
- 继承
- 重载
- 多态：可以理解为同一个父类方法在不同的子类中具有不同的实现形式。多态性是面向对象编程的一个重要概念，它允许不同类型的对象对同一个方法做出不同的响应。

### 类

- 静态属性——属性（成员变量）
- 动态属性——方法（成员方法）

#### 权限修饰符

![权限修饰符](https://s2.loli.net/2023/11/06/xpD7RZwe65IsAn9.png)

#### 成员变量 

定义一个成员变量（也称为实例变量）需要遵循以下形式：

```java
访问修饰符 数据类型 变量名;
```

具体说明如下：

1. **访问修饰符（Access Modifier）**：访问修饰符用于控制成员变量的访问权限。常见的访问修饰符包括 `public`、`private`、`protected` 和默认（无修饰符）。它们决定了哪些部分可以访问该变量。
2. **数据类型（Data Type）**：数据类型指定了变量可以存储的数据类型。例如，`int`、`double`、`String`、自定义类等。变量的数据类型决定了它能够存储的值的范围和操作。
3. **变量名（Variable Name）**：变量名是标识变量的名称。它应遵循命名规范，并具有描述性，以清楚地表示变量的用途。

下面是一个示例的成员变量定义：

```
javaCopy code
public class MyClass {
    public int myVariable;
    private String myString;
    protected double myDouble;
    int myDefaultVariable;
}
```

在上述示例中，定义了一个名为 `MyClass` 的类，其中包含了四个成员变量。`myVariable` 具有 `public` 访问修饰符，可以被任何类访问。`myString` 具有 `private` 访问修饰符，只能在当前类内部访问。`myDouble` 具有 `protected` 访问修饰符，可以被同一包内的类和子类访问。`myDefaultVariable` 没有指定访问修饰符，默认访问级别为包级访问，只能在同一包内的类访问。

> 需要注意的是，成员变量的定义通常放在类的内部，在方法外部。这样定义的成员变量属于类的实例，每个类的实例都会有一份独立的成员变量。可以通过类的实例来访问和修改成员变量的值。

#### 成员方法

定义一个方法需要遵循以下形式：

```java
修饰符 返回类型 方法名(参数列表) {
    // 方法体
    // 执行的代码
    // 可选的 return 语句
}具体说明如下：
```

1. **修饰符（Modifiers）**：修饰符是可选的，用于控制方法的访问权限和其他特性。常见的修饰符包括 `public`、`private`、`protected`、`static`、`final` 等。如果不需要使用修饰符，可以省略。
2. **返回类型（Return Type）**：返回类型指定了方法执行完后返回的值的数据类型。如果方法不返回任何值，则返回类型为 `void`。如果方法返回一个值，则指定相应的数据类型，如 `int`、`double`、`String` 等。
3. **方法名（Method Name）**：方法名是标识方法的名称，应使用合适的命名规范。方法名应具有描述性，以清楚地表示方法的功能。
4. **参数列表（Parameter List）**：参数列表指定了方法接受的输入参数。参数可以有零个或多个，并且每个参数都包含一个数据类型和一个参数名。参数之间用逗号分隔。
5. **方法体（Method Body）**：方法体是方法的实际执行代码。它包含了在方法被调用时要执行的一系列语句。
6. **返回语句（Return Statement）**：如果方法有返回类型，可以使用 `return` 语句来返回一个值。`return` 语句终止方法的执行，并将返回值传递给调用者。

下面是一个示例方法的定义：

```java
public int add(int a, int b) {
    int sum = a + b;
    return sum;
}
```

在上述示例中，方法名为 `add`，返回类型为 `int`，参数列表包含两个参数 `a` 和 `b`，方法体中计算了参数的和，并通过 `return` 语句将结果返回给调用者。

> 如果一个方法中含有与成员变量同名的局部变量，则方法中对这个变量的访问以局部变量进行。类的成员变量和成员方法也可以统称为类成员。

#### 构造函数

> 和Js的构造函数类似，都是在实例化对象的时候需要设置成员变量的值。（初始化实例对象）

**特点：**

- 构造函数是类里面的一种方法，无返回数据类型，但是函数不需要使用void关键字标识。
- 构造函数名与类名一样。

> “如果类中没有明确定义构造方法，编译器会自动创建一个不带参数的默认构造方法。”“只有在类中没有定义任何构造方法时，编译器才会在该类中自动创建一个不带参数的构造方法。”
>

要特别注意的是，如果我们自定义了一个构造方法，那么，编译器就*不再*自动创建默认构造方法：

```java
public class Main {
    public static void main(String[] args) {
        Person p = new Person(); // 编译错误:找不到这个构造方法
    }
}

class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public String getName() {
        return this.name;
    }

    public int getAge() {
        return this.age;
    }
}
```

可以定义多个构造方法，在通过`new`操作符调用的时候，编译器通过构造方法的参数数量、位置和类型自动区分：

```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public Person(String name) {
        this.name = name;
        this.age = 12;
    }

    public Person() {
    }
}
```



#### 局部变量

> 局部变量的作用访问，在于它所处的花括号作用域中

1. 相互不嵌套的作用域中可以同时声明两个名称和类型相同的局部变量

```java
public class Main {
    public static void main(String args[]) {
        for (int i = 0; i < 2; i++) {
            System.out.println('1');
        }
        for (int i = 0; i < 2; i++) {
            System.out.println('2');
        }
    }
}
```

在本实例中两个for循环的作用域没有相互嵌套，是一个对齐的方式，此时可以在两个for循环的作用域定义同一个局部变量名

2. 相互嵌套的作用域中不可以同时声明两个名称和类型相同的局部变量

```java
public class Main {
    public static void main(String args[]) {
        int i = 0;
        for (int i = 0; i < 2; i++) {
            System.out.println('2');
        }
    }
}
```

在本实例中for循环作用域中的局部变量i在外层作用域中存在，这段代码会报错。

#### this关键字

> 指向当前实例对象，可以调用成员变量和成员方法。（与python中的self和javascript中的this类似）

```java
public class Main {
    String name = "test";

    public String test() {
        return "test";
    }

    public void get() {
        System.out.println(this.test() + this.name);
    }

    public static void main(String args[]) {
        Main main = new Main();
        main.get();
    }
}
```

#### 静态变量和静态方法

> 由static修饰的变量和方法被称为静态变量和静态方法。(调用静态成员和静态方法不需要实例对象)

```java
public class Main {
    static final double PI = 3.1415;

    public static String test() {
        return "Hello";
    }

    public static void main(String args[]) {
        System.out.println(Main.PI + Main.test());
    }
}
```

**注：**

- 调用静态成员和静态方法不需要实例对象
- 在静态方法中不可以使用this关键字。
- 在静态方法中不可以直接调用非静态方法。
- 局部变量不可以使用static关键字声明。
- 只有内部类可以使用static关键字声明。

### 方法重载

> 在一个类中，我们可以定义多个方法。如果有一系列方法，它们的功能都是类似的，只有参数有所不同，那么，可以把这一组方法名做成*同名*方法。例如，在`Hello`类中，定义多个`hello()`方法：

```java
class Hello {
    public void hello() {
        System.out.println("Hello, world!");
    }

    public void hello(String name) {
        System.out.println("Hello, " + name + "!");
    }

    public void hello(String name, int age) {
        if (age < 18) {
            System.out.println("Hi, " + name + "!");
        } else {
            System.out.println("Hello, " + name + "!");
        }
    }
}
```

### 继承

> 使用extends关键字，java是单继承。

#### 复用代码

```java
class Person {
    private String name;
    private int age;

    public String getName() {...}
    public void setName(String name) {...}
    public int getAge() {...}
    public void setAge(int age) {...}
}

class Student extends Person {
    // 不要重复name和age字段/方法,
    // 只需要定义新增score字段/方法:
    private int score;

    public int getScore() { … }
    public void setScore(int score) { … }
}
```

#### protected

> 子类无法访问父类的`private`字段或者`private`方法。

```java
class Person {
    private String name;
    private int age;
}

class Student extends Person {
    public String hello() {
        return "Hello, " + name; // 编译错误：无法访问name字段
    }
}
```

这使得继承的作用被削弱了。为了让子类可以访问父类的字段，我们需要把`private`改为`protected`。用`protected`修饰的字段可以被子类访问：

```java
class Person {
    protected String name;
    protected int age;
}

class Student extends Person {
    public String hello() {
        return "Hello, " + name; // OK!
    }
}
```

#### super

> 如果父类没有默认的构造方法，子类就必须显式调用`super()`并给出参数以便让编译器定位到父类的一个合适的构造方法。

```java
class Person {
    protected String name;
    protected int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

class Student extends Person {
    protected int score;

    public Student(String name, int age, int score) {
        super(name, age); // 调用父类的构造方法Person(String, int)
        this.score = score;
    }
}
```

#### 向上转型

问题：如果`Student`是从`Person`继承下来的，那么，一个引用类型为`Person`的变量，能否指向`Student`类型的实例？

```java
Person p = new Student(); // ???
```

测试一下就可以发现，这种指向是允许的！

这是因为`Student`继承自`Person`，因此，它拥有`Person`的全部功能。`Person`类型的变量，如果指向`Student`类型的实例，对它进行操作，是没有问题的！

> 但这样Person变量p只能调用属于Person的成员变量和成员方法，无法调用Student类的成员变量和方法。

向上转型实际上是把一个子类型安全地变为更加抽象的父类型：

```java
Student s = new Student();
Person p = s; // upcasting, ok
Object o1 = p; // upcasting, ok
Object o2 = s; // upcasting, ok
```

注意到继承树是`Student > Person > Object`，所以，可以把`Student`类型转型为`Person`，或者更高层次的`Object`。

#### 向下转型

和向上转型相反，如果把一个父类类型强制转型为子类类型，就是向下转型（downcasting）。例如：

```
Person p1 = new Student(); // upcasting, ok
Person p2 = new Person();
Student s1 = (Student) p1; // ok
Student s2 = (Student) p2; // runtime error! ClassCastException!
```

如果测试上面的代码，可以发现：

`Person`类型`p1`实际指向`Student`实例，`Person`类型变量`p2`实际指向`Person`实例。在向下转型的时候，把`p1`转型为`Student`会成功，因为`p1`确实指向`Student`实例，把`p2`转型为`Student`会失败，因为`p2`的实际类型是`Person`，不能把父类变为子类，因为子类功能比父类多，多的功能无法凭空变出来。

因此，向下转型很可能会失败。失败的时候，Java虚拟机会报`ClassCastException`。

为了避免向下转型出错，Java提供了`instanceof`操作符，可以先判断一个实例究竟是不是某种类型：

> 类似沿着继承的方向判断是否实例是否属于继承中的某个类

```
Person p = new Person();
System.out.println(p instanceof Person); // true
System.out.println(p instanceof Student); // false

Student s = new Student();
System.out.println(s instanceof Person); // true
System.out.println(s instanceof Student); // true

Student n = null;
System.out.println(n instanceof Student); // false
```

`instanceof`实际上判断一个变量所指向的实例是否是指定类型，或者这个类型的子类。如果一个引用变量为`null`，那么对任何`instanceof`的判断都为`false`。

利用`instanceof`，在向下转型前可以先判断：

```
Person p = new Student();
if (p instanceof Student) {
    // 只有判断成功才会向下转型:
    Student s = (Student) p; // 一定会成功
}
```

从Java 14开始，判断`instanceof`后，可以直接转型为指定变量，避免再次强制转型。例如，对于以下代码：

```
Object obj = "hello";
if (obj instanceof String) {
    String s = (String) obj;
    System.out.println(s.toUpperCase());
}
```

可以改写如下：

```
// instanceof variable:
```

### 多态

#### 重写

在继承关系中，子类如果定义了一个与父类方法签名完全相同的方法，被称为重写（Override）。

例如，在`Person`类中，我们定义了`run()`方法：

```
class Person {
    public void run() {
        System.out.println("Person.run");
    }
}
```

在子类`Student`中，覆写这个`run()`方法：

```
class Student extends Person {
    @Override
    public void run() {
        System.out.println("Student.run");
    }
}
```

### 附

#### 运行时

##### instanceof

`instanceof` 运算符是一个在运行时执行的运算符，而不是编译时。它用于检查一个对象是否是指定类或其子类的实例，这个检查是在程序运行时进行的，而不是在编译时。

在 Java 中，由于对象的类型信息在运行时才能确定，编译器在编译时无法确定对象的实际类型。因此，`instanceof` 运算符必须在程序运行时对对象进行动态类型检查。

考虑以下示例：

```java
class Animal {}
class Dog extends Animal {}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog();

        if (animal instanceof Dog) {
            System.out.println("animal is an instance of Dog");
        } else {
            System.out.println("animal is not an instance of Dog");
        }
    }
}
```

在上面的例子中，`animal instanceof Dog` 的判断是在运行时进行的。尽管在编译时声明 `animal` 为 `Animal` 类型，但是它在运行时被实际赋值为 `Dog` 类型的对象，所以 `instanceof` 运算符能够正确地检查出 `animal` 是 `Dog` 类型的实例。

请注意，由于 `instanceof` 是运行时检查，对于 `null` 对象，`instanceof` 运算符始终返回 `false`，因为 `null` 没有任何实际的类型信息。

```java
Animal animal = null;
if (animal instanceof Dog) {
    // This block will not be executed because 'animal' is null
} else {
    System.out.println("animal is not an instance of Dog");
}
```

因此，`instanceof` 运算符在 Java 中是一种用于运行时类型检查的非常有用的工具。

##### getClass

`getClass()` 方法是 `Object` 类中定义的方法，因此在所有的 Java 类中都可用。它返回一个 `Class` 对象，该对象包含有关调用该方法的对象的运行时类型的信息。换句话说，它返回的是对象的实际类的引用。

由于 Java 是一门面向对象的语言，对象的类型信息只能在程序运行时确定。因此，`getClass()` 方法只能在运行时提供对象的实际类型信息。

考虑以下示例：

```java
class Animal {}
class Dog extends Animal {}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog();
        Class<?> clazz = animal.getClass();

        System.out.println(clazz.getName()); // Output: Dog
    }
}在上面的例子中，`getClass()` 方法被调用时，它返回的是 `Dog` 类的 `Class` 对象，而不是 `Animal` 类的 `Class` 对象。这是因为 `animal` 实际上是一个 `Dog` 对象，所以 `getClass()` 方法返回的是 `Dog` 类的信息。
```

需要注意的是，`getClass()` 方法的返回类型是 `Class<?>`，因为它可以表示任意类的信息。你可以使用 `getName()` 方法获取该类的名称。但是在使用 `getClass()` 方法时，要注意对象不能为 `null`，否则会抛出 `NullPointerException`。

总结：`getClass()` 方法是在运行时获取对象的实际类型信息的方法，它返回的是 `Class` 对象，用于表示对象的类的信息。由于类型信息只能在运行时确定，所以 `getClass()` 方法只能在程序运行时提供正确的结果。

