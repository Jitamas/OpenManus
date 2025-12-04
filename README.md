# 👋 OpenManus

> **Notes (Important Fork Information)**
> This fork fixes two common issues users frequently face when working with Daytona and Pillow:
>
> **1. Incorrect Pillow Version**
> The original repository lists Pillow as version **11.x**, which causes installation failures. The correct working version is **10.4.0**.
>
> **2. Daytona Configuration Problems**
> Many users encounter Daytona-related errors. This fork resolves them by ensuring you can add your **Daytona API key** directly inside `config/config.toml` under the root directory.
>
> **Additional Known Issues**
>
> * "Module not found" errors for **Daytona** and **structlog** occur because they are *not* included in the original `requirements.txt` file.
> * This fork **does NOT modify** the `requirements.txt` file. To fix these issues manually:
>
>   * Make sure Daytona is installed.
>   * Install **structlog version 24.1.0**, which resolves the import errors.
>
> These notes are placed here to save you time and frustration before you start installation.

<p align="center">
  <img src="assets/logo.jpg" width="200"/>
</p>

English | [中文](README_zh.md) | [한국어](README_ko.md) | [日本語](README_ja.md)

[![GitHub stars](https://img.shields.io/github/stars/FoundationAgents/OpenManus?style=social)](https://github.com/FoundationAgents/OpenManus/stargazers)
 
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  
[![Discord Follow](https://dcbadge.vercel.app/api/server/DYn29wFk9z?style=flat)](https://discord.gg/DYn29wFk9z)
[![Demo](https://img.shields.io/badge/Demo-Hugging%20Face-yellow)](https://huggingface.co/spaces/lyh-917/OpenManusDemo)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.15186407.svg)](https://doi.org/10.5281/zenodo.15186407)

# 👋 OpenManus

Manus is incredible, but OpenManus can achieve any idea without an *Invite Code* 🛫!

Our team members [@Xinbin Liang](https://github.com/mannaandpoem) and [@Jinyu Xiang](https://github.com/XiangJinyu) (core authors), along with [@Zhaoyang Yu](https://github.com/MoshiQAQ), [@Jiayi Zhang](https://github.com/didiforgithub), and [@Sirui Hong](https://github.com/stellaHSR), we are from [@MetaGPT](https://github.com/geekan/MetaGPT). The prototype is launched within 3 hours and we are keeping building!

It's a simple implementation, so we welcome any suggestions, contributions, and feedback!

Enjoy your own agent with OpenManus!

We're also excited to introduce [OpenManus-RL](https://github.com/OpenManus/OpenManus-RL), an open-source project dedicated to reinforcement learning (RL)- based (such as GRPO) tuning methods for LLM agents, developed collaboratively by researchers from UIUC and OpenManus.

## Project Demo

<video src="https://private-user-images.githubusercontent.com/61239030/420168772-6dcfd0d2-9142-45d9-b74e-d10aa75073c6.mp4" controls="controls" muted="muted" class="d-block rounded-bottom-2 border-top width-fit" style="max-height:640px; min-height: 200px"></video>

## Installation

We provide two installation methods. Method 2 (using uv) is recommended for faster installation and better dependency management.

### Method 1: Using conda

1. Create a new conda environment:

```bash
conda create -n open_manus python=3.12
conda activate open_manus
```

2. Clone the repository:

```bash
git clone https://github.com/FoundationAgents/OpenManus.git
cd OpenManus
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

### Method 2: Using uv (Recommended)

1. Install uv (A fast Python package installer and resolver):

For Linux or Mac:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

For Windows (According to ChatGPT):

```bash
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

2. Clone the repository:

```bash
git clone https://github.com/FoundationAgents/OpenManus.git
cd OpenManus
```

3. Create a new virtual environment and activate it:

```bash
uv venv --python 3.12
source .venv/bin/activate  # On Unix/macOS
# Or on Windows:
# .venv\Scripts\activate
```

4. Install dependencies:

```bash
uv pip install -r requirements.txt
```

### Browser Automation Tool (Optional)

```bash
playwright install
```

## Configuration

OpenManus requires configuration for the LLM APIs it uses. Follow these steps to set up your configuration:

1. Create a `config.toml` file in the `config` directory (you can copy from the example):

```bash
cp config/config.example.toml config/config.toml
```

2. Edit `config/config.toml` to add your API keys and customize settings:

```toml
[llm]
model = "gpt-4o"
base_url = "https://api.openai.com/v1"
api_key = "sk-..."
max_tokens = 4096
temperature = 0.0

[llm.vision]
model = "gpt-4o"
base_url = "https://api.openai.com/v1"
api_key = "sk-..."
```

## Quick Start

```bash
python main.py
```

For MCP tool version:

```bash
python run_mcp.py
```

For unstable multi-agent version:

```bash
python run_flow.py
```

### Custom Adding Multiple Agents

```toml
[runflow]
use_data_analysis_agent = true
```

## How to contribute

We welcome any friendly suggestions and contributions! Create issues or PRs.

## Community Group

<div align="center">
    <img src="assets/community_group.jpg" width="300" />
</div>

## Star History

![Star History Chart](https://api.star-history.com/svg?repos=FoundationAgents/OpenManus\&type=Date)

## Sponsors

Thanks to PPIO for computing support.

## Acknowledgement

Thanks to anthropic-computer-use, browser-use, crawl4ai, AAAJ, MetaGPT, OpenHands, SWE-agent, and stepfun.

## Cite

```bibtex
@misc{openmanus2025,
  author = {Xinbin Liang and Jinyu Xiang and Zhaoyang Yu and Jiayi Zhang and Sirui Hong and Sheng Fan and Xiao Tang},
  title = {OpenManus: An open-source framework for building general AI agents},
  year = {2025},
  publisher = {Zenodo},
  doi = {10.5281/zenodo.15186407},
  url = {https://doi.org/10.5281/zenodo.15186407},
}
```
