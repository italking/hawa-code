# Hawa Code 一个懂你的、智能编程助手
官网：[https://www.hawacode.com](https://www.hawacode.com "一个懂你的、智能编程助手")
## 功能介绍 
代码理解
可以理解复杂代码库，上下文感知理解。自动读取、分析整个项目结构并自主开发，提供相关解决方案。

全栈开发
前后端代码一站式开发，从零构建复杂的系统工程，自动构建项目代码、数据库开发。

多模型支持
支持多种模型调用，用户可以自主选择自己业务匹配和经济实惠的模型。

插件集成
支持 MCP、用户自定义 Command 、 Skill、Subagent ，灵活扩展 。


## 安装
1、执行安装命令
```
npm install -g  @dahawa/hawa-code
```

2、配置 API Key
- 配置文件路径：~/.hcode/config.json
```
{
  "sources": {
    "openai": {
      "base_url": "https://api.openai.com/v1",
      "auth_token": "{apikey}",
      "api_type": "openai",
      "models": ["gpt-5.5", "gpt-5.4-mini"]
    },
    "kimi": {
      "base_url": "https://api.kimi.com/coding",
      "auth_token": "{apikey}",
      "api_type": "anthropic",
      "models": ["K2.5", "K2.6"]
    },
    "qwen-coding": {
      "base_url": "https://coding.dashscope.aliyuncs.com/apps/anthropic",
      "auth_token": "{apikey}",
      "api_type": "anthropic",
      "models": ["qwen3-coder-plus"]
    }
  },

  "routing": {
    "MODEL": [
      { "source": "kimi", "model": "K2.6", "weight": 60 },
      { "source": "openai", "model": "gpt-5.5", "weight": 40 }
    ],
    "SMALL_FAST_MODEL": [
      { "source": "qwen-coding", "model": "qwen3-coder-plus", "weight": 50 },
      { "source": "kimi", "model": "K2.5", "weight": 50 }
    ]
  }
}
```
3、执行启动命令
```
hcode
```
4、Windows 
Hawa Code 完全兼容 Windows ，在 Windows 使用默认使用 PowerShell ，用户指令、Skill、斜杠命令中使用的脚本都需要是 PowerShell。
如果要在 Windows 系统上使用 Shell，需配置如下环境变量，其指向 git bash , 同时确保已经安装了 git。

```
HAWA_CODE_GIT_BASH_PATH={git 安装目录}\bin\bash.exe
```
环境变量配置方式
- 直接在 `~/.hcode/settings.json` 的 `env` 字段中配置（推荐）

