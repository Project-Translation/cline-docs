# 🚀 MCP 快速入门指南

## ❓ 什么是 MCP 服务器？

将 MCP 服务器想象成特殊的助手，它们赋予 Cline 额外的功能！它们让 Cline 能够做一些很酷的事情，比如获取网页内容或处理你的文件。

## ⚠️ 重要：系统要求

停！在继续之前，你必须验证以下要求：

### 必需软件

-   ✅ 最新的 Node.js（v18 或更高版本）

    -   通过运行检查：`node --version`
    -   从以下网址安装：<https://nodejs.org/>

-   ✅ 最新的 Python（v3.8 或更高版本）

    -   通过运行检查：`python --version`
    -   从以下网址安装：<https://python.org/>

-   ✅ UV 包管理器
    -   安装 Python 后，运行：`pip install uv`
    -   通过以下命令验证：`uv --version`

❗ 如果上述任何命令失败或显示旧版本，请在继续之前进行安装/更新！

⚠️ 如果遇到其他错误，请参阅下面的“故障排除”部分。

## 🎯 快速步骤（仅在满足要求后进行！）

### 1. 🛠️ 安装你的第一个 MCP 服务器

1. 从 Cline 扩展中，点击 `MCP 服务器` 选项卡
2. 点击 `编辑 MCP 设置` 按钮

 <img src="https://github.com/user-attachments/assets/abf908b1-be98-4894-8dc7-ef3d27943a47" alt="MCP 服务器面板" width="400" />

3. MCP 设置文件应在 VS Code 的一个选项卡中显示。
4. 用以下代码替换文件内容：

对于 Windows：

```json
{
	"mcpServers": {
		"mcp-installer": {
			"command": "cmd.exe",
			"args": ["/c", "npx", "-y", "@anaisbetts/mcp-installer"]
		}
	}
}
```

对于 Mac 和 Linux：

```json
{
	"mcpServers": {
		"mcp-installer": {
			"command": "npx",
			"args": ["@anaisbetts/mcp-installer"]
		}
	}
}
```

保存文件后：

1. Cline 会自动检测到更改
2. MCP 安装程序将被下载并安装
3. Cline 将启动 MCP 安装程序
4. 你将在 Cline 的 MCP 设置界面中看到服务器状态：

<img src="https://github.com/user-attachments/assets/2abbb3de-e902-4ec2-a5e5-9418ed34684e" alt="带有安装程序的 MCP 服务器面板" width="400" />

## 🤔 下一步做什么？

现在你已经有了 MCP 安装程序，你可以要求 Cline 从以下位置添加更多服务器：

1. NPM 注册表：<https://www.npmjs.com/search?q=%40modelcontextprotocol>
2. Python 包索引：<https://pypi.org/search/?q=mcp+server-&o=>

例如，你可以要求 Cline 安装在 Python 包索引上找到的 `mcp-server-fetch` 包：

```bash
"安装名为 `mcp-server-fetch` 的 MCP 服务器
- 确保更新 MCP 设置。
- 使用 uvx 或 python 运行服务器。"
```

你应该会看到 Cline：

1. 安装 `mcp-server-fetch` Python 包
2. 更新 MCP 设置 JSON 文件
3. 启动服务器并开始运行

MCP 设置文件现在应该看起来像这样：

_对于 Windows 机器：_

```json
{
	"mcpServers": {
		"mcp-installer": {
			"command": "cmd.exe",
			"args": ["/c", "npx", "-y", "@anaisbetts/mcp-installer"]
		},
		"mcp-server-fetch": {
			"command": "uvx",
			"args": ["mcp-server-fetch"]
		}
	}
}
```

你随时可以通过转到客户端的 MCP 服务器选项卡来检查服务器状态。参见上图。

就是这样！🎉 你刚刚赋予了 Cline 一些很棒的新能力！

## 📝 故障排除

### 1. 我在使用 `asdf` 时遇到“未知命令：npx”

有点坏消息。你仍然可以让事情正常运行，但除非 MCP 服务器打包方式有所改进，否则你需要做更多手动工作。一个选择是卸载 `asdf`，但我们假设你不想这样做。

相反，你需要按照上面的说明“编辑 MCP 设置”。然后，正如[这篇文章](https://dev.to/cojiroooo/mcp-using-node-on-asdf-382n)所述，你需要在每个服务器的配置中添加一个“env”条目。

```json
"env": {
        "PATH": "/Users/<user_name>/.asdf/shims:/usr/bin:/bin",
        "ASDF_DIR": "<path_to_asdf_bin_dir>",
        "ASDF_DATA_DIR": "/Users/<user_name>/.asdf",
        "ASDF_NODEJS_VERSION": "<your_node_version>"
      }
```

`path_to_asdf_bin_dir` 通常可以在你的 shell 配置文件（例如 `.zshrc`）中找到。如果你在使用 Homebrew，可以使用 `echo ${HOMEBREW_PREFIX}` 找到目录的起始位置，然后追加 `/opt/asdf/libexec`。

现在有些好消息。虽然不是完美的，但你可以让 Cline 为后续的服务器安装相当可靠地完成这项工作。在 Cline 设置（右上角工具栏按钮）中的“自定义指令”中添加以下内容：
> 在安装 MCP 服务器并编辑 cline_mcp_settings.json 文件时，如果服务器需要使用 `npx` 作为命令，您必须从 "mcp-installer" 条目中复制 "env" 条目，并将其添加到新条目中。这对于服务器在使用时正常工作至关重要。

### 2. 运行 MCP 安装程序时仍然遇到错误

如果您在运行 MCP 安装程序时遇到错误，可以尝试以下方法：

-   检查 MCP 配置文件是否有错误
-   阅读 MCP 服务器的文档，确保 MCP 配置文件使用了正确的命令和参数。👈
-   使用终端直接运行带有参数的命令。这将让您看到 Cline 看到的相同错误。