<div align="center">

<picture>
  <source media="(prefers-color-scheme: light)" srcset="/clustr/logo1.png">
  <img alt="clustr logo" src="/clustr/logo1.png" width="50%" height="50%">
</picture>

(https://x.com/clustr_ai).


<h3>

 [Telegram](https://t.me/clustrportal) | [X](https://x.com/clustr_ai)

</h3>


</div>

---

## Features

### Wide Model Support

clustr supports different models including Claude, GPT, LLaMA and tinygrad, Mistral, LlaVA, Qwen and Deepseek.

### Multi Device Blending

Combine different everyday devices such as your laptops or iPhones to blend your compute resources together and power your own locally hosted super AI agent

### Hardware Blockchain Wallet

Alongside hosting an AI Agent, you can configure and host your own hardware wallets on these devices, your AI agent is bound to the hardware wallet where you manage and store your own tokens.




### Prerequisites

- Python>=3.12.0.
- For Linux with NVIDIA GPU support (Linux-only, skip if not using Linux or NVIDIA):
  - NVIDIA driver - verify with `nvidia-smi`
  - CUDA toolkit - install from [NVIDIA CUDA guide](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#cuda-cross-platform-installation), verify with `nvcc --version`
  - cuDNN library - download from [NVIDIA cuDNN page](https://developer.nvidia.com/cudnn-downloads), verify installation by following [these steps](https://docs.nvidia.com/deeplearning/cudnn/latest/installation/linux.html#verifying-the-install-on-linux:~:text=at%20a%20time.-,Verifying%20the%20Install%20on%20Linux,Test%20passed!,-Upgrading%20From%20Older)


## Installation

The current recommended way to install clustr is from source.
No configuration required - clustr will automatically discover the other device(s).

clustr starts a ChatGPT-like WebUI (powered by [tinygrad tinychat](https://github.com/tinygrad/tinygrad/tree/master/examples/tinychat)) on http://localhost:52415


### Hardware Requirements

- The only requirement to run clustr is to have enough memory across all your devices to fit the entire model into memory. For example, if you are running llama 3.1 8B (fp16), you need 16GB of memory across all devices. Any of the following configurations would work since they each have more than 16GB of memory in total:
  - 2 x 8GB M3 MacBook Airs
  - 1 x 16GB NVIDIA RTX 4070 Ti Laptop
  - 2 x Raspberry Pi 400 with 4GB of RAM each (running on CPU) + 1 x 8GB Mac Mini
    
- clustr is designed to run on devices with heterogeneous capabilities. For example, you can have some devices with powerful GPUs and others with integrated GPUs or even CPUs. Adding less capable devices will slow down individual inference latency but will increase the overall throughput. 

### How to install from source

```sh
git clone https://github.com/ubercreator/clustr.git
cd clustr
pip install -e .
# alternatively, with venv
source install.sh
```
For developers, clustr also starts a ChatGPT-compatible API endpoint on http://localhost:52415/v1/chat/completions. Examples with curl:

#### Llama 3.2 3B:

```sh
curl http://localhost:52415/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
     "model": "llama-3.2-3b",
     "messages": [{"role": "user", "content": "What is the meaning of life?"}],
     "temperature": 0.7
   }'
```

### Troubleshooting

- If running on Mac, MLX has an [install guide](https://ml-explore.github.io/mlx/build/html/install.html) with troubleshooting steps.

### Performance

- There are a number of things users have empirically found to improve performance on Apple Silicon Macs:

1. Upgrade to the latest version of MacOS 15.
2. Run `./configure_mlx.sh`. This runs commands to optimize GPU memory allocation on Apple Silicon Macs.


