# Gemini CLI Docker Based Development Container
AI-Powered Terminal Assistant with Full-Stack Development Environment

This repository provides production-ready Docker images featuring Google's Gemini CLI - an open-source AI agent that brings Gemini 2.5 Pro directly into your terminal - pre-configured with a comprehensive multi-language development stack.​

## What's Inside
Base Development Stack:

1. .NET SDK 10 (latest)
2. Node.js (latest LTS)
3. Python 3 with pip
4. OpenJDK (latest)
5. Gemini CLI (pre-installed and configured)

## Key Features:
1. AI-Assisted Development: Leverage Gemini's 1 million token context window for analyzing large codebases, bug detection, code refactoring, and automated test generation​
2. Ready-to-Code Environment: Zero-configuration development container with all major language runtimes pre-installed
3. Terminal-Native Workflow: Lightning-fast AI assistance without IDE overhead or complex configurations​
4. Built-in Tool Integration: Access to file operations, shell execution, web search, and Model Context Protocol (MCP) server support​
5. Rapid Prototyping: Perfect for quick experimentation, proof-of-concepts, and cross-platform development


## Ideal Use Cases
1. Quick Start Development: Spin up a complete development environment in seconds
2. Cross-Platform Projects: Build applications targeting .NET, Node.js, Python, and Java ecosystems simultaneously
3. AI-Powered Code Analysis: Investigate codebases, understand architecture, and identify bugs using natural language​
4. Prototyping & POCs: Rapidly test ideas across multiple technology stacks
5. CI/CD Pipelines: Standardized build environment for multi-stack projects
6. Learning & Experimentation: Safe, isolated environment for exploring AI-assisted development workflows

## Authentication
Gemini CLI supports multiple authentication methods:​
1. Google Account (60 requests/minute, 1,000 requests/day free tier)​
2. Gemini API Key
3. Google Cloud Vertex AI

Simply run gemini after container launch to authenticate and start developing with AI assistance.

## How to Build and Run the Container
```bash
docker build -t gemini-cli .
docker build -t gemini-cli:v3_devtools -t gemini-cli:v3 -t gemini-cli:v3_0.15 -t gemini-cli:v3-dotnet-node-python-openjdk .
```

Run the container: The CLI can now be run using your new image:
```bash
docker run -it -v .:/context -e GEMINI_API_KEY="<API_key_goes_here>" --entrypoint /bin/bash gemini-cli-image
docker run -it -v .:/context -e GEMINI_API_KEY="<API_key_goes_here>" gemini-cli-image
```
 
When the container runs, the gemini command will execute immediately. The user will be prompted to authenticate by following a link in their browser the first time they use it.

## References
1. [Gemini-CLI API key can be created/found Here](https://aistudio.google.com/api-keys)
1. [Gemini-CLI GitHub location](https://github.com/google-gemini/gemini-cli)
2. [NetworkChuck - Video demonstration about Gemini-CLI usage](https://www.youtube.com/watch?v=MsQACpcuTkU&t=1654s&pp=ygUKZ2VtaW5pIGNsaQ%3D%3D)
3. [Gemini-CLI usage demo reference 2](https://www.youtube.com/watch?v=EPReHLqmQPs)