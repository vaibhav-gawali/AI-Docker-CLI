# fabric-cli (Dockerized)

[Fabric](https://github.com/danielmiessler/fabric) is an open-source framework for managing and executing AI-powered Patterns and workflows.

[Fabric CLI](https://github.com/danielmiessler/fabric) provides a lightweight Dockerized version of the Fabric framework, enabling seamless use of AI-powered Patterns directly from the command line. It packages the Fabric tool into a portable container, making setup consistent across environments without manual installation. With fabric-cli, you can run prompts, process text, scrape content, and integrate AI workflows quickly in any Docker-supported system. Ideal for developers, writers, and researchers who want a ready-to-use, containerized Fabric experience.

---

## 📦 Dockerfile Features
- Based on **Ubuntu 25.10**  
- Includes **Fabric CLI** installed globally  
- Preconfigured with **yt-dlp** for YouTube video processing  
- Portable and consistent environment for Fabric usage  
- Embeds `fabric` directly as the container entrypoint  

---


## 🛠️ Usage
Build the Docker image
```bash
docker build -t fabric-cli .
```

Run the container interactively
```bash
docker run --rm -it vaibhavgawali/fabric-cli:v2_fv1.4.320 --setup
docker run --rm -it vaibhavgawali/fabric-cli:v2_fv1.4.320 --help
```

🧪 Example Commands
Once inside the container, you can run Fabric CLI commands.
fabric youtube https://www.youtube.com/watch?v=wPEyyigh10g&t


Usage examples:
```bash
docker run --rm -it vaibhavgawali/fabric-cli:v2_fv1.4.320 --help
docker run --rm -it -v C:\Temp\.fabric-config:/root/.config/fabric --name fabricvg vaibhavgawali/fabric-cli:v2_fv1.4.320 -y "https://www.youtube.com/watch?v=wPEyyigh10g&t=240s" --stream --pattern summarize
```
Steps:
1. Create local directory on home OS to store fabric configuration. Ex: C:\Temp\.fabric-config (Windows), $HOME (Linux/Mac)
2. Ensure that you map the fabric config dir with docker volume at container location `/root/.config/fabric` when running the container
3. Setup fabric configuration i.e. configure all mandatory plugins, LLM provider, default model etc.
`docker run --rm -it -v C:\Temp\.fabric-config:/root/.config/fabric --name fabricvg vaibhavgawali/fabric-cli:v2_fv1.4.320 --setup`
4. Now you can execute all the fabric commands after setup
`docker run --rm -it -v C:\Temp\.fabric-config:/root/.config/fabric --name fabricvg vaibhavgawali/fabric-cli:v2_fv1.4.320 -y "https://www.youtube.com/watch?v=wPEyyigh10g&t=240s" --stream --pattern summarize`


## Persisting configuration
Fabric stores its configuration in ~/.config/fabric/.env. Mount this path to keep your settings on the host.

## Using a host directory
`mkdir -p $HOME/.fabric-config`

### Run setup to create the .env and download patterns
`docker run --rm -it -v $HOME/.fabric-config:/root/.config/fabric vaibhavgawali/fabric-cli:v2_fv1.4.320 --setup`

Subsequent runs can reuse the same directory:
```bash
docker run --rm -it -v $HOME/.fabric-config:/root/.config/fabric vaibhavgawali/fabric-cli:v2_fv1.4.320 -p your-pattern
```


### Running the server
Expose port 8080 to use Fabric's REST API:
```bash
docker run --rm -it -p 8080:8080 -v $HOME/.fabric-config:/root/.config/fabric vaibhavgawali/fabric-cli:v2_fv1.4.320 --serve
```
The API will be available at http://localhost:8080.

Fabric project GitHub repo: https://github.com/danielmiessler/Fabric

Download fabric-cli docker image from dockerHub: https://hub.docker.com/repository/docker/vaibhavgawali/fabric-cli
