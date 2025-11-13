## How to Build and Run the Container
```bash
docker build -t gemini-cli-image .
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