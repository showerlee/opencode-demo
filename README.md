# opencode-demo

This repo aims to help to learn anything in OpenCode.

## Custom Provider Setup Guide
This guide walks you through configuring a custom OpenAI-compatible provider in OpenCode.

### Features

- Simple project structure for quick testing
- Example provider setup for OpenCode
- Support for multiple DeepSeek model entries

### 1. Installed opencode on your MacOS CLI

```
# Install latest opencode
curl -fsSL https://opencode.ai/install | bash

# Verify the installation
opencode --version
```

### 2. Init your workspace

Create a `opencode-demo` dir as your opencode workspace

```
mkdir -p /Users/xxx/Desktop/opencode/repo/opencode-demo
cd /Users/xxx/Desktop/opencode/repo/opencode-demo
```

### 3. Set custom provider in workspace

Create an opencode provider config `opencode.json` in your workspace

```bash
vi opencode.json
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {
    "plus7": {
      "npm": "@ai-sdk/openai-compatible",
      "name": "plus7",
      "options": {
        "baseURL": "https://tbnx.plus7.plus/v1"
      },
      "models": {
        "deepseek-chat": {
          "name": "deepseek-chat"
        },
        "deepseek-reasoner": {
          "name": "deepseek-reasoner"
        },
        "deepseek-r1": {
          "name": "deepseek-r1"
        }
      }
    }
  }
}
```

The configuration is stored in [opencode.json](opencode.json). It defines a provider named `plus7` and includes example models such as `deepseek-chat`, `deepseek-reasoner`, and `deepseek-r1`

### 4. Add credentials interactively

Make sure your provider credentials are available in your environment before running requests.

```bash
opencode auth login
```

Then follow the prompts:
1. Scroll down and select **Other**
2. Enter Provider ID: `plus7`
3. Paste your `plus7` API key

### 5. Launch OpenCode with the Plus7 model

Launch opencode with provider model `plus7/deepseek-chat` and you're ready to go.

```bash
# Lanch opencode in CLI mode
opencode -m plus7/deepseek-chat

# Non-interactive run mode
opencode run -m plus7/deepseek-chat "Write a quicksort implementation in Python"
```

More model options for `plus7`
  - plus7/deepseek-chat
  - plus7/deepseek-reasoner 
  - plus7/deepseek-r1

### 6. Verify credentials

```bash
opencode auth list
┌  Credentials ~/.local/share/opencode/auth.json
│
●  plus7 api
│
└  1 credentials
```

You should see `plus7` listed under credentials.

### 7. Test the API endpoint directly

```bash
curl https://tbnx.plus7.plus/v1/models -H "Authorization: Bearer YOUR_API_KEY"
```

## Documentation

- https://opencode.ai/docs/cli/
- https://opencode.ai/docs/providers/#custom-provider
- https://my.feishu.cn/docx/V1nPdJM8MowfeZxyIt6chSpMnYc
