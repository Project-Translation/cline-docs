# 使用 Cline 安装基本开发工具 | 新手coder

当你开始编程时，你需要在电脑上安装一些基本的开发工具。Cline 可以帮助你以安全、引导的方式安装所需的一切。

## 基本工具

以下是你开发所需的核心工具：

-   **Homebrew**：macOS 的包管理器，方便安装其他工具
-   **Node.js & npm**：用于 JavaScript 和 Web 开发
-   **Git**：用于跟踪代码变更并与他人协作
-   **Python**：许多开发工具使用的编程语言
-   **其他实用工具**：如 wget 和 jq 等工具，帮助下载文件和处理数据

## 让 Cline 安装一切

复制以下提示并粘贴到 Cline 中：

```bash
你好，Cline！我想为软件开发设置我的 Mac。你能帮我安装基本的开发工具吗？比如 Homebrew、Node.js、Git、Python 以及其他常用的编码工具。我希望你能一步步指导我，解释每个工具的作用，并确保一切都安装正确。
```

## 会发生什么

1. Cline 将首先安装 Homebrew，它就像开发工具的“应用商店”
2. 使用 Homebrew，Cline 随后会安装其他基本工具，如 Node.js 和 Git
3. 对于每个安装步骤：
    - Cline 会显示它要运行的确切命令
    - 你需要在命令运行前批准每个命令
    - Cline 将验证每次安装是否成功

## 为什么这些工具很重要

-   **Homebrew**：让在 Mac 上安装和更新开发工具变得简单
-   **Node.js & npm**：用于：
    -   使用 React 或 Next.js 构建网站
    -   运行 JavaScript 代码
    -   安装 JavaScript 包
-   **Git**：帮助你：
    -   保存代码的不同版本
    -   与其他开发者协作
    -   备份你的工作
-   **Python**：用于：
    -   运行开发脚本
    -   数据处理
    -   机器学习项目

## 注意事项

-   安装过程是交互式的 - Cline 将指导你完成每一步
-   某些安装可能需要输入你的电脑密码。输入时，屏幕上不会显示任何字符。这是正常的，是保护密码安全的功能。只需输入密码并按 Enter 键即可。

**示例：**

```bash
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
Password:
```

_在此输入你的密码，尽管屏幕上不会显示任何内容。完成后按 Enter 键。_

-   所有命令都会在运行前展示给你以获得批准
-   如果遇到任何问题，Cline 将帮助解决

## 新手coder的额外提示

### 理解终端

**终端** 是一个你可以输入命令与电脑交互的应用程序。在 macOS 上，你可以通过在 Spotlight 中搜索“Terminal”来打开它。

**示例：**

```bash
$ open -a Terminal
```

### 理解 VS Code 功能

#### VS Code 中的终端

VS Code 中的 **终端** 允许你直接在编辑器内运行命令。你可以通过转到 `视图 > 终端` 或按下 `` Ctrl + ` `` 来打开它。

**示例：**

```bash
$ node -v
v16.14.0
```

#### 文档视图

**文档视图** 是你编辑代码文件的地方。你可以通过点击屏幕左侧的 **资源管理器** 面板中的文件来打开它们。

#### 问题部分

VS Code 中的 **问题** 部分显示代码中的任何错误或警告。你可以通过点击灯泡图标或转到 `视图 > 问题` 来访问它。

### 常见功能

-   **命令行界面 (CLI)**：这是一个基于文本的界面，你可以在其中输入命令与电脑交互。起初可能看起来有些吓人，但它对开发者来说是一个强大的工具。
-   **权限**：有时，你需要为某些应用程序或命令授予权限。这是一种安全措施，确保只有受信任的应用程序才能对你的系统进行更改。

## 下一步

安装这些工具后，你就可以开始编码了！返回[新手coder的 Cline 入门指南](../getting-started-new-coders/README.md)继续你的旅程。