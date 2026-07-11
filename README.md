# opencode-demo

This repository is a minimal demo for using OpenCode with a custom provider configuration.

## Overview

The project includes a sample OpenCode configuration file that connects to a custom OpenAI-compatible endpoint defined in [opencode.json](opencode.json).

## Features

- Simple project structure for quick testing
- Example provider setup for OpenCode
- Support for multiple DeepSeek model entries

## Native OpenCode Installation

### macOS / Linux

Install OpenCode with the official installer:

```bash
curl -fsSL https://opencode.ai/install | bash
```

Verify the installation:

```bash
opencode --version
```

### Quick Start

1. Install OpenCode using the command above.
2. Open this project folder in your terminal.
3. Start OpenCode:

```bash
opencode
```

4. Make sure your provider credentials are available in your environment before running requests.

## Configuration

The configuration is stored in [opencode.json](opencode.json). It defines a provider named `plus7` and includes example models such as `deepseek-chat`, `deepseek-reasoner`, and `deepseek-r1`.

## Notes

This demo is intentionally simple and designed as a starting point for experimenting with OpenCode in a local project.
