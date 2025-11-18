# TinyExt

TinyExt 是一个基于经典TINY语言的扩展编译器项目，使用Qt框架构建图形用户界面，提供了完整的词法分析、语法分析和可视化功能。
<img width="1081" height="653" alt="屏幕截图 2025-11-18 171304" src="https://github.com/user-attachments/assets/6eea5951-1456-4afe-bf5c-09aa1ab8870a" />
<img width="1078" height="649" alt="屏幕截图 2025-11-18 171238" src="https://github.com/user-attachments/assets/9c4da0ed-2503-434c-a1dc-ce19ce6076a8" />

## 🎯 项目概述

TinyExt 是在经典TINY编译器基础上开发的扩展版本，支持更多语言特性，包括：
- 扩展的运算符（+=、%、幂运算）
- 位运算符（AND、OR、NOT）
- 增强的比较运算符（>=、<=、!=）
- 正则表达式操作符
- FOR循环结构
- 图形化语法树展示

## 🛠️ 技术栈

- **编程语言**: C++17
- **GUI框架**: Qt 6.10.0
- **构建系统**: qmake
- **开发环境**: Qt Creator
- **编译器**: MinGW 64-bit

## 📋 功能特性

### 核心功能
- ✅ **词法分析**: 识别TINY语言的所有标记类型
- ✅ **语法分析**: 构建完整的抽象语法树(AST)
- ✅ **语义分析**: 类型检查和符号表管理
- ✅ **错误处理**: 详细的语法错误报告
- ✅ **代码生成**: 生成目标代码

### 扩展功能
- 🔧 **图形界面**: 直观的Qt界面，支持文件操作
- 📊 **语法树可视化**: 树形结构展示语法分析结果
- 🔍 **缩放功能**: 支持语法树的放大缩小查看
- 📁 **文件管理**: 打开、保存TINY源文件
- 📋 **语法高亮**: 增强的代码显示效果

### 支持的语言特性
- 基本语句：IF-ELSE、REPEAT-UNTIL、READ、WRITE
- 扩展语句：FOR-TO-DOWNTO、复合赋值运算
- 表达式：算术运算、逻辑运算、位运算
- 数据类型：整数、布尔值
- 变量声明和使用

## 🚀 快速开始

### 环境要求
- Qt 6.10.0 或更高版本
- MinGW 64-bit 编译器
- Qt Creator (推荐)

### 构建步骤
1. 克隆项目到本地
```bash
git clone [your-repository-url]
cd TinyExt
```

2. 使用Qt Creator打开 `TinyExt.pro` 文件

3. 配置构建套件（Desktop Qt 6.10.0 MinGW 64-bit）

4. 点击构建按钮编译项目

5. 运行生成的可执行文件

### 基本使用
1. **打开文件**: 点击"选择文件"按钮，选择TINY源文件
2. **语法分析**: 点击"分析"按钮进行编译
3. **查看结果**: 在树形控件中查看语法树结构
4. **保存结果**: 可以保存分析结果到文件

## 📁 项目结构

```
TinyExt/
├── src/                    # 源代码文件
│   ├── main.cpp           # 程序入口
│   ├── dialog.cpp/.h      # 主窗口实现
│   ├── analyze.cpp/.h     # 语义分析
│   ├── scan.cpp/.h        # 词法分析
│   ├── parse.cpp/.h       # 语法分析
│   ├── util.cpp/.h        # 工具函数
│   ├── vision.cpp/.h      # 可视化相关
│   └── globals.h          # 全局定义
├── forms/                  # UI文件
│   └── dialog.ui          # 主窗口界面
├── build/                  # 构建输出
├── background.jpg         # 背景图片
├── TinyExt.pro            # Qt项目文件
└── README.md              # 项目说明
```

## 🔧 编译器架构

### 编译流程
1. **词法分析** (Scanner): 将源代码分解为标记序列
2. **语法分析** (Parser): 构建抽象语法树
3. **语义分析** (Analyzer): 类型检查和符号表构建
4. **代码生成** (Code Generator): 生成目标代码

### 关键数据结构
- **TreeNode**: 语法树节点，包含类型、属性和子节点
- **TokenType**: 标记类型枚举，包含所有支持的标记
- **符号表**: 管理变量声明和作用域

## 🎯 TINY语言示例

```tiny
{ Sample TINY program }
read x; { input an integer }
if x > 0 then { don't compute if x <= 0 }
    fact := 1;
    repeat
        fact := fact * x;
        x := x - 1
    until x = 0;
    write fact { output factorial of x }
end
```

## 🚀 扩展功能示例

```tiny
{ 扩展的TINY程序 }
for i := 1 to 10 do
    write i;
    if i % 2 = 0 then
        write i * i
    enddo;

{ 使用复合赋值和位运算 }
x += 5;
y := x AND 15;
z := x OR y;
```

## 🔍 开发说明

### 添加新特性
1. 在 `globals.h` 中定义新的标记类型
2. 在 `scan.cpp` 中实现词法分析
3. 在 `parse.cpp` 中实现语法分析
4. 在 `analyze.cpp` 中实现语义分析
5. 更新UI以支持新功能

### 调试技巧
- 使用 `TraceScan` 查看词法分析过程
- 使用 `TraceParse` 查看语法分析过程
- 使用 `TraceAnalyze` 查看语义分析过程

## 🤝 贡献

欢迎提交Issue和Pull Request来改进项目。

## 📞 联系方式

如有问题或建议，请通过GitHub Issues联系。

---

**TinyExt** - 让编译器学习更直观、更有趣！
