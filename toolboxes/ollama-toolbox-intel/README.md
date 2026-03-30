# OLLAMA Toolbox with Intel GPU Support

This toolbox provides a pre-configured environment for running OLLAMA with Open WebUI, optimized for Intel ARC GPUs.

## Features
- OLLAMA with Mistral model support
- Open WebUI for a user-friendly interface
- Intel ARC GPU acceleration
- No home directory sharing

## Usage

### Create and enter the toolbox
```bash
toolbox create --image ghcr.io/akurpanek/toolboxes/ollama-toolbox-intel:latest ollama-intel
toolbox enter ollama-intel
```

### Start OLLAMA and Open WebUI
```bash
ollama pull mistral
ollama serve &
open-webui serve --port 8080
```

### Access Open WebUI
Open your browser and navigate to:
```
http://localhost:8080
```

### Verify Intel GPU Usage
```bash
sycl-ls
```

## Notes
- Ensure your host system has the Intel GPU drivers installed.
- The toolbox is configured to use the Intel ARC GPU for acceleration.