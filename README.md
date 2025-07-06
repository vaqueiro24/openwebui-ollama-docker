# openwebui-ollama-docker

A collection of docker compose files that can spin up an openwebui / ollama stack for both Intel and AMD cards. Tested on both Intel Arc A770 and Radeon RX 6650 XT cards.

OpenWebUI will be accessible at http://[my-servers-ip]:8080

## Intel

Environment variables were set to the recommended values for an Intel Arc A-Series graphics card, according to this [page](https://ipex-llm-latest.readthedocs.io/en/latest/doc/LLM/Overview/install_gpu.html).

Run openwebui by cloning this git repo, opening a terminal and running this command:

`docker-compose -f docker-compose-intel.yml up`

## AMD

Environment variable HSA_OVERRIDE_GFX_VERSION set in order to run on my Radeon RX 6650 XT. 
If your Radeon graphics card is not officially supported by ROCm, you can use this list:
  - for GCN 5th gen based GPUs and APUs HSA_OVERRIDE_GFX_VERSION=9.0.0
  - for RDNA 1 based GPUs and APUs HSA_OVERRIDE_GFX_VERSION=10.1.0
  - for RDNA 2 based GPUs and APUs HSA_OVERRIDE_GFX_VERSION=10.3.0
  - for RDNA 3 based GPUs and APUs HSA_OVERRIDE_GFX_VERSION=11.0.0
Taken from this [thread](https://discuss.linuxcontainers.org/t/rocm-and-pytorch-on-amd-apu-or-gpu-ai/19743).

Run openwebui by cloning this git repo, opening a terminal and running this command:

`docker-compose -f docker-compose-amd.yml up`
