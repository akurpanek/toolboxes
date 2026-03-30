# OLLAMA Toolbox with Intel ARC GPU Support

This toolbox provides a ready-to-use environment for running OLLAMA with Open WebUI and Mistral models, optimized for Intel ARC GPUs.

## Features

- Podman and Podman Compose for container management
- Intel GPU drivers and tools for ARC support
- Pre-configured OLLAMA and Open WebUI via Podman Compose
- No need to share the home directory

## Usage

1. Build the toolbox image using the provided workflow.
2. Enter the toolbox: `toolbox enter ollama-toolbox-intel`
3. Start the services: `podman-compose up -d`
4. Access Open WebUI at `http://localhost:8080`

## Notes

- Ensure your user has access to `/dev/dri` for GPU passthrough.
- The toolbox uses volumes for OLLAMA and Open WebUI data, so no home directory sharing is required.