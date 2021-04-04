# 学习笔记
## 形式语言：
- 0型 无限制文法
    - `?::= ?`
- 1型 上下文相关文法
    - `?<A>?::= ?<B>?`
- 2型 上下文无关文法
    - `<A>::= ?`
- 3型 正则文法
    - `<A>::= <A>?`
    - `<A>::= ?<A>`（不允许）
- 0 > 1 > 2 > 3


## 产生式：
- BNF：
    1. 语法结构:
        - 结构名： < >
        - 构成：
            - 基础结构：终结符 （可以理解为无法继续展开）
            - 复合结构：非终结符
    2. 使用引号与中间字符作为终结符（即字符串）
    3. 可以使用括号，变成一组
    4. 展开种类：
        - `*` 重复多次
        - `|` 表示或
        - `+` 表示至少一次


    5. 描述四则运算 `1 + 3 * 3`
        - 终结符： `Number`， `+`，`-`，`*`，`/`
        - 非终结符： `AddtiveExpression`, `MultiplicativeExpression`
        - ```
            <MuliplicativeExpression> ::= <Number> | 
            <MuliplicativeExpression> "*" <Number> |
            <MuliplicativeExpression> "/" <Number>
          ```
        - ```
            <AddtiveExpression> ::= <MuliplicativeExpression> | 
            <AddtiveExpression> "+" <MuliplicativeExpression> |
            <AddtiveExpression> "-" <MuliplicativeExpression>
          ```
        
    6. 描述包含括号的四则运算 `1 + (3 * 3 + 5) * 6`
        - 终结符： `Number`， `+`， `-`， `*`， `/`, `(`, `)`
        - 非终结符： `AddtiveExpression`, `MultiplicativeExpression`,`Expression`
        - ```
            <MuliplicativeExpression> ::= <Number> | 
            <MuliplicativeExpression> "*" <Number> |
            <MuliplicativeExpression> "/" <Number>
          ```
        - ```
            <AddtiveExpression> ::= <MuliplicativeExpression> | 
            <AddtiveExpression> "+" <MuliplicativeExpression> |
            <AddtiveExpression> "-" <MuliplicativeExpression>
          ```
        - ```
            <Expression> ::= <AddtiveExpression> | "(" <Expression> ")" 
          ```

        
## 语言分类：
### 用途
- 数据描述语言
    `JSON`, `HTML`, `XML`, `SQL`, `CSS`.
- 编程语言
    `C`, `C++`, `Go`
    
### 表达方式
- 声明式语言
    `JSON`, `函数编程语言`
- 命令式寓言
    `C`, `C++`, `JavaScript`



## 图灵完备性：
###  命令式 图灵机（图灵）
- goto
- if/while
### 声明式语言 lambda（邱奇）
- 递归


## 动态与静态
### 动态
- 用户设备/服务器设备
- 产品实际运行时
- Runtime
### 静态
- 程序员设备
- 产品开发时
- Compiletime

## 类型系统
- 动态类型/静态类型（运行的时候，是否保留了类型）
- 强类型与弱类型（类型转换是否会默认转换）
- 复合类型
    - 结构体
    - 函数签名
- 子类型
- 泛性
    - 逆变/协变

## 一般命令式编程语言组成
### Atom
- 关键字 Identifier
- 直接量 Literal
### Expression
- Atom
- Operrator
- Punctuator
###  Statement
- Expression
- Keyworld
- Punctuator
###  Structure
- Function
- Class
- Process
- Namespace
### Program
- Program
- Module
- Package
- Library
### 语法 ->（语义） 运行时







    
## 重学JavaScript
### Atom
#### 1. Grammar
- Literal
    - Number
        - 0, 0., .2, 1e3
        - 0b111
        - 0o666
        - 0xFF
    - String
        - ""
        - ''
        - \`` Template Tokens
            - \`ab${
            - \}abc${
            - \}abc`
            - \`abc`
    - Object
        - Base: {}, ., [], Object.defineProperty
        - Object.create, Object.setPrototypeOf, Object.getPropertyOf
        - new / class / extends
        - new / function / prototype
    - Function Object 
        - 带有[[call]]行为
    - Array
        - [[length]] 动态变化
    - Variable
    - Keywords
    - Whitespace
    - Line Terminator
#### 2. Runtime
- Types
    - Number
        - IEEE 754 Double Float
            - Sign（1）
            - Exponent（11）
            - Fraction （52）        
    - String
        - Character    
            - ASCII
            - Unicode
            - USC
            - GB
                - GB2312
                - GBK(GB13000)
                - GB18030
            - ISO-8859
            - BIG5
        - CodePoint
        - Encoding
            - UTF8
            - UTF16
    - Boolean
    - Null
        - null（关键字）
        - 有值但为空
    - Undefined
        - undefined（非关键字）
        - void 0; (用来产生undefined)
        - 未定义
    - Object
        - *行为必须要改变状态*      
        - K， V
            - K 类型
                - Symbol（具有唯一性，仅支持变量访问）
                - String
        - Property
           
            - Data Property
                - [[value]]
                - writable
                - emumerable
                - configureable
            - Accessor Properry
                - get
                - set
                - enumerable
                - configureable

        - [[ptototype]]
        - 内存地址唯一性/对象唯一性
        - 链式行为/ 原型链
    - Symbol
        - 专门用于JavaScript属性名
    - BigInt
- Execution Context
