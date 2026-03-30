# OLLAMA Toolbox with Intel ARC GPU Support (for Distrobox)

This toolbox provides a ready-to-use environment for running OLLAMA with Open WebUI and Mistral models, optimized for Intel ARC GPUs using **Distrobox**.

## Features

- Podman and Podman Compose for container management
- Intel GPU drivers and tools for ARC support
- Pre-configured OLLAMA and Open WebUI via Podman Compose
- No need to share the home directory

## Prerequisites

- Distrobox installed on your system
- Intel ARC GPU drivers installed on the host

## Usage

1. **Create the Distrobox container:**
   ```bash
   distrobox create --name ollama-toolbox-intel --image ghcr.io/akurpanek/ollama-toolbox-intel:latest
   ```

2. **Enter the container:**
   ```bash
   distrobox enter ollama-toolbox-intel
   ```

3. **Start the services:**
   ```bash
   cd /opt/ollama
   podman-compose up -d
   ```

4. **Access Open WebUI at:** [http://localhost:8080](http://localhost:8080)

## Notes

- Ensure your user has access to `/dev/dri` for GPU passthrough.
- The toolbox uses volumes for OLLAMA and Open WebUI data, so no home directory sharing is required.
- Make sure the Intel GPU drivers are installed on the host system.

## Troubleshooting

- If you encounter permission issues, ensure your user is in the `render` group:
  ```bash
  sudo usermod -aG render $USER
  ```
- Restart your system after adding the user to the `render` group.