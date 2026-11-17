# Hello-word-of-fine-tuning
<<<<<<< HEAD
These are some of the "Hello World" of fine-tuning large language models, built with LLaMA-Factory. Learn and Enjoy!
=======

These are some of the "Hello World" of fine-tuning large language models, built with [LLaMA-Factory](https://github.com/hiyouga/LLaMA-Factory). Learn and Enjoy!

**If you find any mistakes or disagree with any of the explanations, please do not hesitate to [submit an issue](https://github.com/AidinZe/Hello-word-of-fine-tuning/issues/new). I welcome any feedback, positive or negative!**

## About

Fine-tuning used to be something only big labs could do. With tools like LLaMA-Factory and methods like **LoRA / QLoRA**, anyone with a single GPU (or even a free Colab!) can adapt a model to their own task.

This repo walks you through the "Hello World" examples of fine-tuning, from zero:

1. **What is fine-tuning?** — why and when you need it
2. **What is LoRA / QLoRA?** — efficient fine-tuning without touching all weights
3. **Hands-on**: instruction-tune a small model on a tiny dataset
4. **Chat with your model**: export and inference

## Requirements

- Python >= 3.9
- PyTorch >= 2.0
- A GPU with >= 8GB VRAM (or Google Colab free tier for QLoRA)
- [Docker](https://docker.com) (optional, see [docker/](docker/))

## Project Structure

```
hello-word-of-fine-tuning/
├── notebooks/        # step-by-step "Hello World" notebooks
│   ├── 01_introduction_to_fine_tuning.ipynb
│   ├── 02_lora_qlora_explained.ipynb
│   └── 03_finetune_with_llama_factory.ipynb
├── configs/          # ready-to-use LLaMA-Factory training configs
│   ├── hello_lora.yaml
│   └── hello_qlora.yaml
├── data/             # tiny example datasets + dataset_info.json
├── docker/           # Dockerfile to run everything in a container
└── README.md
```

## Quick Start

### Option 1: Run locally

```bash
git clone https://github.com/hiyouga/LLaMA-Factory
cd LLaMA-Factory
pip install -e ".[torch,metrics]"
```

Copy our data and configs:

```bash
cp -r ../hello-word-of-fine-tuning/data/* ./data/
cp ../hello-word-of-fine-tuning/configs/*.yaml ./examples/
llamafactory-cli train examples/hello_lora.yaml
```

### Option 2: Docker

```bash
cd docker
docker build -t hello-finetune .
docker run --gpus all -it hello-finetune

# inside the container:
llamafactory-cli train examples/hello/hello_lora.yaml
```

### Option 3: Google Colab

Open `notebooks/03_finetune_with_llama_factory.ipynb` in Colab (free T4 GPU is enough for QLoRA) and follow the cells.

## Roadmap (learn in order)

| Step | Notebook | What you learn |
|------|----------|----------------|
| 1 | `01_introduction_to_fine_tuning.ipynb` | What/why/when of fine-tuning |
| 2 | `02_lora_qlora_explained.ipynb` | LoRA, QLoRA, hyperparameters |
| 3 | `03_finetune_with_llama_factory.ipynb` | Full hands-on training + chat |

## License

MIT
>>>>>>> master
