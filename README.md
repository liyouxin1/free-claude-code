<div align="center">

<!-- 项目标题区域：根据访客的浅色/深色主题自动切换对应的 Logo 图片。 -->
<h1>
  <picture>
    <source media="(prefers-color-scheme: light)" srcset="assets/free-claude-code-wordmark-light.svg">
    <img src="assets/free-claude-code-wordmark-dark.svg" alt="Free Claude Code" width="610">
  </picture>
</h1>

<!-- 项目状态徽章：分别链接到许可证、Python 版本、包管理器、测试、类型检查、代码格式化和日志工具的相关页面。 -->
[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-2e7d32.svg?style=for-the-badge)](https://github.com/Alishahryar1/free-claude-code/blob/main/LICENSE)
[![Python 3.14](https://img.shields.io/badge/python-3.14-3776ab.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/downloads/)
[![Package Manager: uv](assets/package-manager-uv.svg)](https://github.com/astral-sh/uv)
[![Testing: Pytest](https://img.shields.io/badge/Testing-Pytest-ad1457.svg?style=for-the-badge)](https://github.com/Alishahryar1/free-claude-code/actions/workflows/tests.yml)
[![Type Checker: Ty](https://img.shields.io/badge/Type%20Checker-ty-fdd835.svg?style=for-the-badge)](https://pypi.org/project/ty/)
[![Formatter: Ruff](https://img.shields.io/badge/Formatter-ruff-bf4b00.svg?style=for-the-badge)](https://github.com/astral-sh/ruff)
[![Logging: Loguru](https://img.shields.io/badge/logging-loguru-00695c.svg?style=for-the-badge)](https://github.com/Delgan/loguru)

<!-- 页面内导航：点击文字可跳转到 README 下方对应章节；括号内是各章节的锚点名称。 -->
[快速开始](#quick-start) · [服务提供商](#choose-a-provider) · [连接客户端](#connect-your-client) · [可选集成](#optional-integrations) · [管理安装](#manage-your-installation)

</div>

<p align="center">
  <em>本项目为独立开源项目，与 Anthropic 无关联，也未获其认可。Claude 和 Claude Code 是 Anthropic 的商标。</em>
</p>

## 功能特性

- 将任意受支持的编程代理接入任意受支持服务提供商的模型。
- 支持 12 种编程代理：[Claude Code](https://code.claude.com/docs/en/overview)、[Codex](https://github.com/openai/codex)、[Pi](https://github.com/earendil-works/pi)、[OpenCode](https://github.com/anomalyco/opencode)、[Cline](https://github.com/cline/cline)、[Hermes](https://github.com/NousResearch/hermes-agent)、[DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness)、[Grok Build](https://github.com/xai-org/grok-build)、[Muse Code](https://research.meta.ai/blog/introducing-muse-code-and-muse-spark-1-2/)、[Aider](https://aider.chat/)、[Antigravity CLI](https://antigravity.google/docs/getting-started/) 和 [VS Code Chat](https://code.visualstudio.com/)。
  - 保留原生流式输出、工具调用和交错思考能力，发挥最佳性能。
  - 对 Claude Code，可将 [Fable](https://www.anthropic.com/claude/fable)、[Opus](https://www.anthropic.com/claude/opus)、[Sonnet](https://www.anthropic.com/claude/sonnet) 和 [Haiku](https://www.anthropic.com/claude/haiku) 路由到受支持的模型。
- 支持 61 家服务提供商，包括免费、付费、订阅和本地服务。
  - 每月提供超过 13 亿个免费 token。
  - FCC 遵循服务提供商的服务条款；若某项集成不再被允许，便会将其移除。
- 可通过终端、桌面应用（[Codex App](https://learn.chatgpt.com/docs/app)、[Claude Desktop](https://claude.ai/download) 和 [DeepSeek Desktop](https://github.com/deepseek-ai/deepseek-harness)）、IDE 扩展（[VS Code](https://code.visualstudio.com/) 和 [JetBrains](https://www.jetbrains.com/)）、手机端（[Discord](https://discord.com/) 和 [Telegram](https://telegram.org/)），或通过浏览器中的原生 Code 会话使用。
  - Discord 和 Telegram 支持使用本地 [Whisper](https://github.com/openai/whisper) 或 [NVIDIA NIM](https://docs.nvidia.com/nim/speech/latest/asr/deploy-asr-models/whisper.html) 转录语音消息。
- 使用 [RTK](https://github.com/rtk-ai/rtk) 和 [Headroom](https://github.com/headroomlabs-ai/headroom)，最多可减少 90% 的 token 用量。
- 提供先进的可靠性功能，即使服务提供商发生故障，也能继续编写代码：
  - 自动重试。
  - 可配置的速率限制。
  - 可配置的并发控制。
  - 自动切换备用模型或服务提供商。
  - 自动切换多个 API 密钥。

免费额度及其限制由各服务提供商决定，且可能随时调整。

> **几个常见术语：**「服务提供商」是提供模型或 API 的平台；「模型」是实际回答问题、生成代码的 AI；「编程代理」是你使用的编码工具，例如 Claude Code；API 是软件之间通信的接口；token 是模型处理文本的计量单位，不等同于汉字或单词；OAuth 是通过网页登录授权的方式，通常不需要手动复制 API 密钥。

<div align="center">
  <img src="assets/pic.png" alt="Claude Code 正在通过 Free Claude Code 运行" width="700">
  <p><em>Claude Code 正在通过 FCC 运行。</em></p>
</div>

<div align="center">
  <img src="assets/browser-code-session.png" alt="FCC 中的原生 Codex 浏览器会话，展示模型控制和代码仓库探索" width="700">
  <p><em>FCC 浏览器界面中的原生 Codex 会话。</em></p>
</div>

<a id="quick-start"></a>

## 快速开始

<a id="install"></a>

### 1. 安装

macOS/Linux:

```bash
curl -fsSL "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install.sh" | sh
```

Windows PowerShell:

```powershell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install.ps1")))
```

出现提示时，至少选择一种编程代理；也可以为受支持的代理启用 [RTK](https://github.com/rtk-ai/rtk) + [Headroom](https://github.com/headroomlabs-ai/headroom) token 优化。

### 2. 启动 FCC

#### Windows

从桌面或「开始」菜单打开 **Free Claude Code**。

#### macOS

从桌面或「应用程序」文件夹打开 **Free Claude Code**。

#### Linux

运行：

```bash
fcc-server
```

FCC 启动后会打开管理界面。在 Windows 和 macOS 上，可通过系统托盘或菜单栏图标打开管理界面、重启或退出。运行 `fcc-server` 时，请保持终端窗口打开。

<a id="nvidia-nim-provider"></a>

### 3. 配置 NVIDIA NIM

1. 在 [build.nvidia.com/settings/api-keys](https://build.nvidia.com/settings/api-keys) 创建 API 密钥。
2. 打开服务器日志中显示的管理界面网址。
3. 在 **Providers（服务提供商）** 中打开 NVIDIA NIM，点击 **Add key（添加密钥）**，粘贴密钥，然后点击 **Save（保存）**。
4. `MODEL` 可保留默认值 `nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b`，也可以在模型下拉菜单中搜索并选择其他模型。
5. 点击 **Apply（应用）** 保存模型选择。

如需使用 bearer token 保护本地代理，请在管理界面中启用 **Proxy Authentication（代理身份验证）**。

<div align="center">
  <img src="assets/admin-page.png" alt="Free Claude Code 管理界面" width="700">
</div>

### 4. 运行编程代理

Claude Code:

```bash
fcc-claude
```

Codex:

```bash
fcc-codex
```

Pi:

```bash
fcc-pi
```

OpenCode 2:

```bash
fcc-opencode
```

Cline:

```bash
fcc-cline
```

Hermes:

```bash
fcc-hermes
```

DeepSeek Harness Web:

```bash
fcc-dsh
```

Grok Build:

```bash
fcc-grok
```

Muse Code:

```bash
fcc-muse
```

Aider:

```bash
fcc-aider
```

Antigravity CLI（请先在「集成」页面连接）：

```bash
fcc-agy
```

<a id="model-picker"></a>

<div align="center">
  <img src="assets/cc-model-picker.png" alt="Claude Code 模型选择器中的 FCC 模型" width="700">
  <p><em>在 Claude Code 原生的 <code>/model</code> 选择器中选择 FCC 模型。</em></p>
</div>

<a id="choose-a-provider"></a>

## 选择服务提供商

1. 点击下方服务提供商链接，查看其密钥、模型或配置说明。
2. 在管理界面中配置相应设置。若要使用 OpenAI / ChatGPT 订阅，请改用 **Providers → OAuth providers**。
3. 在 `MODEL` 下拉菜单中搜索并选择模型。如果服务提供商无法列出模型，请手动输入 `<provider-id>/<exact-provider-model-id>`。
4. 点击 **Apply（应用）**。

> **界面英文速查：**管理界面（Admin UI）里的菜单和按钮名称目前是英文，下面保留原文方便你对照：
> - **Providers**：服务提供商设置；**Cloud providers**：云端服务；**OAuth providers**：通过网页登录授权的服务（通常不需要填写 API 密钥）。
> - **Model Config**：模型配置；**Model Routing**：模型路由，即决定请求交给哪个模型处理。
> - **Integrations**：集成设置；**Messaging**：消息机器人设置；**Voice**：语音消息设置。
> - **Connect / Disconnect**：连接 / 断开；**Add key**：添加密钥；**Save**：保存当前设置；**Apply**：应用设置。
> - **Refresh models**：重新获取模型列表；**Test**：测试服务连接；**Model IDs**：模型 ID 列表。

> **怎么理解模型名称：**`MODEL` 是默认模型设置。列表中的示例通常由“服务提供商前缀/模型 ID”组成，例如 `groq/llama-3.3-70b-versatile`；如果要手动填写，需使用服务提供商实际提供的准确模型 ID。API 密钥是用于验证账号权限的凭据，请勿公开或提交到代码仓库。

可选：在 **Model Config** 下添加有序的 **Fallback Models（备用模型）** 列表。此设置适用于所有已连接的客户端。请求失败后，系统可能会尝试多个服务提供商，并在成功前产生用量。

服务提供商弹窗支持设置多个编号 API 密钥。使用 **Add key（添加密钥）** 添加密钥，可删除密钥行，也可拖动行柄调整顺序。FCC 默认使用密钥 1。

如需使用其他 API 端点，请打开 **Providers（服务提供商）→ Custom providers（自定义服务商）→ Add provider（添加服务商）**。填写 API 基础 URL（服务商提供的接口地址）、可选密钥和 API 格式。将 **Model IDs（模型 ID）** 留空可自动发现模型，也可每行填写一个上游模型 ID（服务商原始提供的模型标识）。保存后，在 **Model Config（模型配置）** 中选择模型。

> **备用模型提示：**`Fallback Models` 是主模型不可用时依次尝试的候补列表，不是同时运行的模型。添加多个不同服务商的模型可以提高可用性，但失败的尝试也可能产生费用或消耗免费额度。

> **服务商列表怎么看：**表格中的环境变量名（如 `OPENROUTER_API_KEY`）用于标识密钥或地址设置；通常可直接在管理界面的相应服务商设置中填写，不需要自己修改系统环境变量。`MODEL` 示例是模型选择器里的模型名称格式，尖括号中的内容（如 `<model-id>`）表示需要替换成实际值。

<details>
<summary><strong>服务提供商列表</strong></summary>

| 服务提供商 | 管理界面设置 | `MODEL` 示例 |
| --- | --- | --- |
| [NVIDIA NIM](https://build.nvidia.com/settings/api-keys) | `NVIDIA_NIM_API_KEY` | `nvidia_nim/nvidia/nemotron-3-ultra-550b-a55b` |
| [OpenRouter](https://openrouter.ai/keys) | `OPENROUTER_API_KEY` | `open_router/openrouter/free` |
| [Groq](https://console.groq.com/keys) | `GROQ_API_KEY` | `groq/llama-3.3-70b-versatile` |
| [ClinePass](https://docs.cline.bot/getting-started/clinepass) | `CLINE_API_KEY` | `cline_pass/cline-pass/kimi-k3` |
| [OpenAI / ChatGPT](https://learn.chatgpt.com/docs/auth) | 在管理界面连接 ChatGPT | `openai/<model-id>` |
| [OpenAI API](https://platform.openai.com/api-keys) | `OPENAI_API_KEY` | `openai_api/gpt-5.6-sol` |
| [GitHub Copilot](https://docs.github.com/en/copilot/how-tos/copilot-sdk/auth/authenticate) | 在管理界面连接 GitHub Copilot | `github_copilot/<model-id>` |
| [xAI (Grok)](https://console.x.ai/team/default/api-keys) | `XAI_API_KEY` | `xai/grok-4.5` |
| [Alibaba Cloud](https://www.alibabacloud.com/help/en/model-studio/get-api-key) | `ALIBABA_CLOUD_API_KEY` | `alibaba_cloud/<model-id>` |
| [QwenCloud Token Plan](https://home.qwencloud.com/api-keys) | `QWENCLOUD_API_KEY` | `qwencloud/qwen3.7-plus` |
| [QwenCloud Coding Plan](https://home.qwencloud.com/api-keys) | `QWENCLOUD_CODING_API_KEY` | `qwencloud_coding/qwen3.7-plus` |
| [Together AI](https://api.together.ai/settings/api-keys) | `TOGETHER_API_KEY` | `together/zai-org/GLM-5.2` |
| [DeepInfra](https://deepinfra.com/dash/api_keys) | `DEEPINFRA_API_KEY` | `deepinfra/deepseek-ai/DeepSeek-V4-Flash` |
| [SiliconFlow](https://cloud.siliconflow.com/account/ak) | `SILICONFLOW_API_KEY` | `siliconflow/Qwen/Qwen3-32B` |
| [Nebius Token Factory](https://tokenfactory.nebius.com/project/api-keys) | `NEBIUS_API_KEY` | `nebius/Qwen/Qwen3-30B-A3B` |
| [Chutes](https://chutes.ai/docs/getting-started/authentication) | `CHUTES_API_KEY` | `chutes/Qwen/Qwen3-32B-TEE` |
| [Featherless AI](https://featherless.ai/account/api-keys) | `FEATHERLESS_API_KEY` | `featherless/Qwen/Qwen3-32B` |
| [Agnes AI](https://agnes-ai.com/) | `AGNES_API_KEY` | `agnes/agnes-2.0-flash` |
| [ZenMux](https://zenmux.ai/platform/pay-as-you-go) | `ZENMUX_API_KEY` | `zenmux/deepseek/deepseek-v4-flash-free` |
| [W&B Inference](https://wandb.ai/settings) | `WANDB_API_KEY` | `wandb/openai/gpt-oss-20b` |
| [Anthropic](https://platform.claude.com/settings/keys) | `ANTHROPIC_API_KEY` | `anthropic/<model-id>` |
| [Azure OpenAI](https://learn.microsoft.com/azure/foundry/openai/how-to/chatgpt) | `AZURE_OPENAI_API_KEY` and `AZURE_OPENAI_BASE_URL` | `azure_openai/<deployment-name>` |
| [Google AI Studio (Gemini)](https://aistudio.google.com/apikey) | `GEMINI_API_KEY` | `gemini/models/gemini-3.1-flash-lite` |
| [Google Vertex AI](https://cloud.google.com/vertex-ai/generative-ai/docs/start/openai) | `VERTEX_PROJECT_ID` + ADC | `vertex/google/gemini-3.5-flash` |
| [DeepSeek](https://platform.deepseek.com/api_keys) | `DEEPSEEK_API_KEY` | `deepseek/deepseek-chat` |
| [Mistral La Plateforme](https://console.mistral.ai/) | `MISTRAL_API_KEY` | `mistral/devstral-small-latest` |
| [Mistral Codestral](https://console.mistral.ai/) | `CODESTRAL_API_KEY` | `mistral_codestral/codestral-latest` |
| [OpenCode Zen](https://opencode.ai/auth) | `OPENCODE_API_KEY` | `opencode_zen/gpt-5.3-codex` |
| [OpenCode Go](https://opencode.ai/auth) | `OPENCODE_API_KEY` | `opencode_go/minimax-m2.7` |
| [Vercel AI Gateway](https://vercel.com/docs/ai-gateway/models-and-providers) | `AI_GATEWAY_API_KEY` | `vercel/openai/gpt-5.5` |
| [Amazon Bedrock](https://console.aws.amazon.com/bedrock/) | `AWS_BEARER_TOKEN_BEDROCK` | `bedrock/openai.gpt-oss-120b` |
| [Hugging Face Inference Providers](https://huggingface.co/settings/tokens) | `HUGGINGFACE_API_KEY` | `huggingface/Qwen/Qwen3-Coder-480B-A35B-Instruct:fastest` |
| [Cohere](https://dashboard.cohere.com/api-keys) | `COHERE_API_KEY` | `cohere/command-a-plus-05-2026` |
| [Wafer](https://wafer.ai/) | `WAFER_API_KEY` | `wafer/DeepSeek-V4-Pro` |
| [Kimi API](https://platform.moonshot.ai/console/api-keys) | `KIMI_API_KEY` | `kimi/kimi-k2.5` |
| [Kimi Code](https://www.kimi.com/code/console) | `KIMI_CODE_API_KEY` | `kimi_code/k3` |
| [MiniMax](https://platform.minimax.io/user-center/basic-information/interface-key) | `MINIMAX_API_KEY` | `minimax/MiniMax-M3` |
| [Cerebras Inference](https://cloud.cerebras.ai/) | `CEREBRAS_API_KEY` | `cerebras/gpt-oss-120b` |
| [SambaNova](https://cloud.sambanova.ai/apis) | `SAMBANOVA_API_KEY` | `sambanova/Meta-Llama-3.3-70B-Instruct` |
| [Kilo.ai](https://kilo.ai) | `KILO_API_KEY` | `kilo/kilo-auto/free` |
| [Fireworks AI](https://fireworks.ai/account/api-keys) | `FIREWORKS_API_KEY` | `fireworks/accounts/fireworks/models/llama-v3p3-70b-instruct` |
| [Novita AI](https://novita.ai/settings/key-management) | `NOVITA_API_KEY` | `novita/deepseek/deepseek-v4-flash-0731` |
| [Cloudflare Workers AI](https://developers.cloudflare.com/workers-ai/) | `CLOUDFLARE_API_TOKEN` and `CLOUDFLARE_ACCOUNT_ID` | `cloudflare/@cf/moonshotai/kimi-k2.6` |
| [Z.ai Coding Plan](https://z.ai/manage-apikey/apikey-list) | `ZAI_API_KEY` | `zai/glm-5.2` |
| [Z.ai API (pay as you go)](https://z.ai/manage-apikey/apikey-list) | `ZAI_API_KEY` | `zai_api/glm-4.7-flash` |
| [TokenRouter](https://www.tokenrouter.com/) | `TOKENROUTER_API_KEY` | `tokenrouter/moonshotai/kimi-k3-free` |
| [NaraRoute](https://router.bynara.id/) | `NARAROUTE_API_KEY` | `nararoute/kimi-k3-free` |
| [Poolside AI](https://platform.poolside.ai/) | `POOLSIDE_API_KEY` | `poolside/poolside/laguna-s-2.1` |
| [LLM7.io](https://dash.llm7.io/) | `LLM7_API_KEY` | `llm7/default` |
| [Scaleway](https://console.scaleway.com/iam/api-keys) | `SCW_SECRET_KEY` | `scaleway/deepseek/deepseek-v4-flash` |
| [Lightning AI](https://lightning.ai/) | `LIGHTNING_API_KEY` | `lightning/lightning-ai/Qwen3.8-27B` |
| [Experiential Labs](https://platform.experientiallabs.ai/) | `EXPLABS_API_KEY` | `experiential/union-alpha` |
| [Cheaper Inference](https://cheaperinference.com/signup) | `CHEAPER_INFERENCE_API_KEY` | `cheaperinference/gpt-5.4-mini` |
| [OrcaRouter](https://www.orcarouter.ai/) | `ORCAROUTER_API_KEY` | `orcarouter/deepseek/deepseek-v4-flash-free` |
| [Atlas Cloud](https://console.atlascloud.ai/api-keys) | `ATLASCLOUD_API_KEY` | `atlascloud/deepseek-ai/deepseek-v4-flash` |
| [xKiro](https://xkiro.com/) | `XKIRO_API_KEY` | `xkiro/qwen/qwen3.7-flash:free` |
| [Opper](https://platform.opper.ai/) | `OPPER_API_KEY` | `opper/claude-sonnet-4-6` |
| [Ollama Cloud](https://ollama.com/settings/keys) | `OLLAMA_API_KEY` | `ollama_cloud/qwen3-coder:480b` |
| [LM Studio](https://lmstudio.ai/) | `LM_STUDIO_BASE_URL` | `lmstudio/<model-id>` |
| [llama.cpp](https://github.com/ggml-org/llama.cpp) | `LLAMACPP_BASE_URL` | `llamacpp/<model-id>` |
| [Ollama](https://ollama.com/) | `OLLAMA_BASE_URL` | `ollama/<model-tag>` |

</details>

<details>
<summary><strong>各服务提供商的配置说明</strong></summary>

- OpenAI / ChatGPT 使用 ChatGPT 订阅，而非 API 密钥。在管理界面中打开
  **Providers → OAuth providers → OpenAI / ChatGPT → Connect**，然后在浏览器中完成登录。
  这是网页登录授权；连接后，请重启已运行的代理。
- Anthropic 使用单独计费的 API 密钥。在
  **Providers → Cloud providers → Anthropic → Configure** 中添加密钥，然后选择已发现的模型。
  **Configure** 表示配置。多工作区密钥还需要设置 `ANTHROPIC_WORKSPACE_ID`。
- OpenAI API 使用单独的 Platform API 密钥。在
  **Providers → Cloud providers → OpenAI API → Configure** 中填写密钥。模型列表可能包含
  不适用于编程请求的模型 ID，请选择文本生成模型。
- GitHub Copilot 使用已登录的 GitHub 账号及其订阅。先将
  [Copilot CLI 1.0.83](https://github.com/github/copilot-cli/releases/tag/v1.0.83)
  安装到 PATH 中，然后选择 **Providers → OAuth providers → GitHub Copilot → Connect**。
  完成登录后，在模型选择器中选择 `github_copilot/<model-id>`。
  可用模型和配额取决于订阅类型及组织策略。连接后，请重启已运行的代理。
- Azure OpenAI 使用 Azure 资源中的部署名称。将 `AZURE_OPENAI_BASE_URL` 设置为完整的 v1
  端点，例如 `https://YOUR-RESOURCE-NAME.openai.azure.com/openai/v1/`，并选择支持
  Chat Completions 的部署。如果部署未显示在模型下拉菜单中，请将部署名称作为自定义模型标识填写。
- Mistral Codestral 使用与 Mistral La Plateforme 不同的密钥。
- Kimi Code 订阅密钥使用 `kimi_code/` 前缀；Kimi API 余额密钥使用 `kimi/` 前缀。
  根据 [Kimi 社区指南](https://www.kimi.com/code/docs/en/kimi-code/community-guidelines.html)，
  Kimi Code 计划适用于个人交互式编程代理用途。
- Alibaba Cloud 使用 Model Studio 按量付费密钥，默认区域为新加坡。
  如需使用其他区域或工作区，请将 `ALIBABA_CLOUD_BASE_URL` 设置为对应的
  [OpenAI 兼容端点](https://www.alibabacloud.com/help/en/model-studio/base-url)，
  并确保 URL 以 `/compatible-mode/v1` 结尾。密钥和端点必须属于同一区域。
- QwenCloud Coding Plan 密钥使用 `qwencloud_coding/` 前缀；QwenCloud Token Plan 密钥使用
  `qwencloud/` 前缀。两种密钥和端点不能混用。根据
  [Coding Plan 条款](https://www.alibabacloud.com/help/en/model-studio/coding-plan)，
  Coding Plan 适用于本地、个人交互式编程代理用途。
- OpenCode Zen 和 OpenCode Go 共用 `OPENCODE_API_KEY`，但模型前缀分别为
  `opencode_zen/` 和 `opencode_go/`。
- 使用 Amazon Bedrock 时，将 `BEDROCK_BASE_URL` 设置为与 API 密钥相同区域的 URL，并选择列表中的模型。
- Vertex AI 使用 Google Application Default Credentials，而非 API 密钥。在本地运行一次
  `gcloud auth application-default login`。也支持服务账号文件和附加的服务账号。设置
  `VERTEX_PROJECT_ID`；也可以将 `VERTEX_LOCATION` 从默认值 `global` 改为其他区域。
- Cloudflare 必须同时配置 API token 和账号 ID。
- 对于 Ollama Cloud，请使用模型选择器中显示的准确模型 ID。本地 Ollama 使用独立的 `ollama/` 前缀。
- 编程代理建议使用支持工具调用的模型。本地模型还需要足够的上下文窗口，以容纳代理的系统提示和工具定义。

</details>

<details>
<summary><strong>本地服务提供商配置</strong></summary>

FCC 启动时会自动从正在运行的本地服务器发现模型。如果之后才启动服务器，请在管理界面中点击 **Refresh models（刷新模型）**，将该服务器的模型添加到选择器。

> 这里的“本地”是指模型服务运行在你自己的电脑上，而不是通过云端 API 调用；使用前仍需先安装并启动对应的本地模型服务。

### LM Studio

启动 LM Studio 本地服务器并加载支持工具调用的模型，然后使用 LM Studio 显示的模型标识，并添加 `lmstudio/` 前缀。默认 URL 为 `http://localhost:1234/v1`。

### llama.cpp

启动 `llama-server`，启用其 OpenAI 兼容的 Chat Completions API，并为模型配置足够的上下文窗口。使用本地模型 ID，并添加 `llamacpp/` 前缀。`LLAMACPP_BASE_URL` 默认为 `http://localhost:8080/v1`。

### Ollama

```bash
ollama pull llama3.1
ollama serve
```

使用 `ollama list` 显示的标签，并添加 `ollama/` 前缀。`OLLAMA_BASE_URL` 默认为 `http://localhost:11434`。

服务提供商卡片会显示已检测的端点和响应时间；如果本地服务器不可用，也会显示相应提示。启动服务器或修正设置后，点击 **Test（测试）** 刷新模型列表。

</details>

<details>
<summary><strong>可选：按模型层级路由</strong></summary>

`MODEL` 是所有请求的默认模型。为 `MODEL_FABLE`、`MODEL_OPUS`、`MODEL_SONNET` 或 `MODEL_HAIKU` 选择模型，即可单独覆盖 Claude Code 对应层级的模型。选择 **None（无）** 则使用 `MODEL`。

在 **Admin UI（管理界面）→ Model Config（模型配置）** 中，按 FCC 在所选模型失败时的尝试顺序添加 **Fallback Models（备用模型）**。每个备用模型都可单独设置推理强度：**Inherit（继承）**、**Off（关闭）**、**From client（使用客户端设置）**、**Low（低）**、**Medium（中）**、**High（高）**、**X-High（极高）** 或 **Max（最高）**。

在底部一行选择模型、推理强度和 API 密钥编号，然后点击 **+（添加）**。**Key 1**、**Key 2** 等对应服务提供商设置中的密钥编号。可直接修改选项、拖动行柄调整顺序，或点击红色垃圾桶按钮移除备用模型。

**Inherit（继承）**保留原始请求最终确定的推理设置。**From client（使用客户端设置）**采用编程代理发送的推理强度或 token 预算，并跳过全局或层级设置。同一模型可以选择不同的密钥编号。

</details>

<details>
<summary><strong>推理控制</strong></summary>

打开 **Admin UI（管理界面）→ Model Config（模型配置）→ Model Routing（模型路由）**，为每个模型选择推理强度。**Default Effort（默认推理强度）**默认为 **From client（使用客户端设置）**；Fable、Opus、Sonnet 和 Haiku 默认为 **Inherit（继承）**。

| 选项 | 说明 |
| --- | --- |
| **From client（使用客户端设置）** | 使用编程代理发送的推理强度；如果未发送，则保留服务提供商默认值。 |
| **Off（关闭）** | 请求禁用推理。 |
| **Low（低）**、**Medium（中）**、**High（高）**、**X-High（极高）** 或 **Max（最高）** | 使用所选推理级别覆盖客户端设置。 |
| **Inherit（继承）** | 层级覆盖使用 Default Effort；备用模型保留原始请求最终确定的推理强度。 |

</details>

<a id="connect-your-client"></a>

## 连接客户端

通过 FCC 启动器启动时，服务器会自动运行。

如需集成编辑器或应用，请先安装客户端并启动 FCC，然后打开 **Admin UI（管理界面）→ Integrations（集成）**，点击对应卡片上的 **Connect（连接）**。

- **VS Code 中的 Claude Code**：安装 [Claude Code 扩展](https://marketplace.visualstudio.com/items?itemName=anthropic.claude-code)。
- **VS Code Chat**：安装最新版 [VS Code](https://code.visualstudio.com/)，连接后，在内置的 Chat 模型选择器中选择 FCC 模型。
- **Claude Desktop**：安装 [Claude Desktop](https://claude.ai/download)。连接或断开前请完全退出应用，完成后再重新打开。断开连接后可恢复正常的 Claude 登录方式。
- **VS Code 和应用中的 Codex**：安装 [Codex 扩展](https://marketplace.visualstudio.com/items?itemName=openai.chatgpt)或 Codex App。
- **DeepSeek Harness Desktop**：连接前先安装并打开应用一次。新建会话即可使用 FCC 模型。
- **JetBrains ACP 中的 Claude Code**：在 JetBrains AI Assistant 中安装 Claude Agent 并启动一次，然后在 FCC 中点击 **Connect（连接）**。重新打开 IDE，选择 **Claude Code (FCC)** 并新建聊天。JetBrains 更新代理后，请先重启 FCC 再新建聊天。IDE 必须安装在标准安装目录中。

连接后请重新加载 VS Code，或重启应用/IDE。在 Codex 和 Claude Desktop 中，从模型选择器里选择 FCC 模型。FCC 提示设置已更新时，请重新加载或重启客户端。如需移除集成，请点击对应卡片上的 **Disconnect（断开连接）**。

如需单独完成 Claude Code 初始设置，请打开 **Admin UI（管理界面）→ Integrations（集成）→
Claude Code onboarding（Claude Code 初始设置）** 并点击 **Complete onboarding（完成初始设置）**。连接 VS Code 中的 Claude Code 也会自动完成初始设置。

FCC 和要配置的客户端必须在同一台电脑、同一用户环境中运行。

<a id="optional-integrations"></a>

## 可选集成

在 **Admin UI（管理界面）→ Messaging（消息）** 中配置集成，然后点击 **Apply（应用）**。

> **字段说明：**`Messaging Platform` 是要使用的平台（填 `discord` 或 `telegram`）；`Bot Token` 是创建机器人后获得的访问密钥；`Allowed Discord Channels` 是允许机器人工作的 Discord 频道；`Allowed Telegram User ID` 是允许使用机器人的 Telegram 用户数字 ID；`Allowed Directory` 是机器人可以访问的本机文件夹绝对路径。请勿公开 Bot Token。

<details>
<summary><strong>Discord 机器人</strong></summary>

1. 在 [Discord Developer Portal](https://discord.com/developers/applications) 中创建机器人。
2. 启用 **Message Content Intent（消息内容意图）**，并授予机器人读取、发送、查看消息历史记录和 **Manage Messages（管理消息）** 权限，以便 `/clear` 能够删除用户提示消息。
3. 将 **Messaging Platform** 设置为 **discord**。
4. 填写 **Discord Bot Token**、**Allowed Discord Channels** 和绝对路径形式的 **Allowed Directory**。
5. 应用设置；如收到提示，请重启服务器。

</details>

<details>
<summary><strong>Telegram 机器人</strong></summary>

1. 通过 [@BotFather](https://t.me/BotFather) 创建机器人。
2. 通过 [@userinfobot](https://t.me/userinfobot) 获取数字形式的用户 ID。在群组中，请授予机器人删除消息的权限。
3. 将 **Messaging Platform** 设置为 **telegram**。
4. 填写 **Telegram Bot Token**、**Allowed Telegram User ID** 和绝对路径形式的 **Allowed Directory**。
5. 应用设置；如收到提示，请重启服务器。

</details>

### 消息命令

| 命令 | 功能 |
| --- | --- |
| `/stats` | 显示会话状态。 |
| 单独发送 `/stop` | 取消所有任务。 |
| 回复 `/stop` | 仅取消所选请求，其他排队中的请求继续执行。 |
| 单独发送 `/clear` | 清除此聊天中的所有 FCC 对话及其消息。 |
| 回复 `/clear` | 删除所选消息及其后续回复，保留其他对话。 |

<details>
<summary><strong>语音消息</strong></summary>

所有安装版本均包含 NVIDIA NIM 转录支持。在 **Admin UI（管理界面）→ Messaging（消息）→ Voice（语音）** 中启用语音消息，选择 `nvidia_nim`，并选取受支持的模型。在 **Providers（服务提供商）** 页面配置 **NVIDIA NIM API key（NVIDIA NIM API 密钥）**。

如需在 CPU 或 CUDA 上本地运行 Whisper，请使用本地语音选项重新运行安装程序：

> **CPU** 使用电脑的中央处理器进行计算，通常无需额外配置；**CUDA** 使用兼容的 NVIDIA 显卡加速。没有 NVIDIA 显卡或不确定如何选择时，使用 CPU 选项。

macOS/Linux：

在 CPU 或 CUDA 上本地运行 Whisper：

```bash
curl -fsSL "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install.sh" | sh -s -- --voice-local
```

使用 CUDA 13.0 本地运行 Whisper：

```bash
curl -fsSL "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install.sh" | sh -s -- --voice-local --torch-backend cu130
```

Windows PowerShell：

在 CPU 或 CUDA 上本地运行 Whisper：

```powershell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install.ps1"))) -VoiceLocal
```

使用 CUDA 13.0 本地运行 Whisper：

```powershell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install.ps1"))) -VoiceLocal -TorchBackend cu130
```

安装本地支持后，请重启 `fcc-server`。在 **Admin UI（管理界面）→ Messaging（消息）→ Voice（语音）** 中启用语音消息，选择 `cpu`（中央处理器）或 `cuda`（NVIDIA 显卡加速），并选择 Whisper 模型。需要授权才能访问的本地模型还需要设置 `HUGGINGFACE_API_KEY`（Hugging Face API 密钥）。

</details>

<a id="manage-your-installation"></a>

## 管理安装

运行 `fcc-server --version` 可在不启动 FCC 的情况下检查已安装版本。

### 更新

停止所有正在运行的 FCC 命令，然后运行：

```sh
fcc-update
```

更新程序会安装经过验证的稳定版 FCC 及其对应的安装程序。

如果 `fcc-update` 不可用或运行失败，请尝试再次运行[安装命令](#install)。

如果 FCC 已是最新版本，但你想重新安装或更改可选组件，请直接运行[安装程序](#install)。

如需本地语音支持，请添加 `--voice-local`（macOS/Linux）或 `-VoiceLocal`（Windows）；如果需要指定 PyTorch 后端，也请添加 `--torch-backend` 或 `-TorchBackend` 选项。

### 在原生 Windows 上使用 Muse Code

仅安装或更新 Muse Code：

```powershell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install-muse.ps1")))
```

移除 FCC 安装的 Muse Code，但保留其数据：

```powershell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/uninstall-muse.ps1")))
```

卸载 FCC 不会卸载 Muse Code。

### 卸载

卸载前请停止所有正在运行的 FCC 命令，并退出已连接的桌面应用或编辑器。

**将移除**

- Free Claude Code，包括桌面启动器和相关命令
- `~/.fcc/`

**将保留**

- uv 和 Python
- 已安装的编程代理、RTK 和 Headroom

macOS/Linux：

```bash
curl -fsSL "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/uninstall.sh" | sh
```

Windows PowerShell：

```powershell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/uninstall.ps1")))
```

## 项目链接

如果安装后遇到问题，请运行以下命令，并将输出粘贴到错误报告中。

```bash
fcc-doctor
```

- [报告错误或提出功能请求](https://github.com/Alishahryar1/free-claude-code/issues)
- [贡献指南](CONTRIBUTING.md)

## 许可证

本项目仅采用 GNU Affero 通用公共许可证第 3 版（`AGPL-3.0-only`）。详情请参阅 [LICENSE](LICENSE)。
