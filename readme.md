# 🚀 AI Tools in Docker

A curated collection of Dockerized AI-powered developer tools for rapid prototyping, automation, and productivity.This repository provides ready-to-use Dockerfiles and workflows so developers can run powerful AI utilities in isolated, reproducible environments—without the hassle of manual setup.

## 📦 Why Dockerized AI Tools?

1. Consistency: Run tools in a clean, reproducible environment.
2. Portability: Works across Linux, macOS, and Windows.
3. Simplicity: No dependency hell—just docker run.
4. Productivity: Focus on building, not configuring.

## 🛠️ Included Tools

| Tool           | Description                                                              | Upstream Project                                   |
| -------------- | ------------------------------------------------------------------------ | -------------------------------------------------- |
| **Fabric**     | A framework for AI-powered text manipulation, automation, and workflows. | [Fabric](https://github.com/danielmiessler/Fabric) |
| **OpenCode**   | AI coding assistant for generating, refactoring, and explaining code.    | [OpenCode](https://opencode.ai)                    |
| **Gemini-CLI** | Command-line interface for Google Gemini AI models.                      | [Gemini CLI](https://geminicli.com/)               |

🚀 Getting Started

Prerequisites

Docker installed on your system.

Clone the Repository
```bash
git clone https://github.com/vaibhav-gawali/AI-Docker-CLI.git
cd AI-Docker-CLI
```

Build and Run a Tool

Each tool has its own Dockerfile inside the repository. Example for Fabric:

## Build the image
```bash
docker build -t fabric-cli ./fabric
```

## Run the container
```bash
docker run -it --rm fabric-cli --help
```

# 🌟 Acknowledgments
1. [Daniel Miessler](https://github.com/danielmiessler) for **Fabric**
2. [OpenCode](https://opencode.ai) team ([OpenCode GitHub repo](https://github.com/sst/opencode))
3. [Gemini CLI](https://geminicli.com) developers. (Google [gemini-cli GitHub repo](https://github.com/google-gemini/gemini-cli))