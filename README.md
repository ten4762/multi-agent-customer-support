# 多智能体协作客服系统

一个基于 Python、LangChain 和 LangGraph 构建的智能客服系统，能够通过多智能体协作处理航班、酒店、租车等旅行咨询与预订问题。

## ✨ 核心特性

- **多智能体协作**: 主智能体自动路由，由航班、酒店等专用子智能体处理特定任务
- **工具分级与安全确认**: 区分安全工具和敏感工具，敏感操作需用户确认后执行[reference:0]
- **状态管理与记忆**: 维护对话状态，支持上下文记忆[reference:1]
- **可观测性**: 集成 LangSmith，便于调试和性能追踪[reference:2]

## 🏗️ 系统架构

系统由 **Vectorizer** (知识库向量化) 和 **Customer Support Chat** (对话系统) 两个核心服务组成[reference:3]。

## 🚀 快速开始

### 环境要求
- Python 3.12+
- Poetry
- Docker & Docker Compose

### 安装与运行

1. **克隆项目**
   ```bash
   git clone https://github.com/ten4762/multi-agent-rag-customer-support.git
   cd multi-agent-rag-customer-support

2. **配置环境变量**
复制 .dev.env 为 .env，并填入你的 OpenAI API Key。

3. **安装依赖**
bash
poetry install

4. **生成向量数据**
bash
poetry run python vectorizer/app/main.py

5. **启动向量数据库**
bash
docker compose up qdrant -d

6. **运行客服系统**
bash
poetry run python ./customer_support_chat/app/main.py

## 📁 项目核心结构

- `customer_support_chat/`: 核心对话系统
- `vectorizer/`: 知识库向量化服务

## 📄 开源协议

本项目基于 [MIT License](LICENSE) 开源。