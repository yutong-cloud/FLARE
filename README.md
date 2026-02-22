```markdown
<div align="center">

# 🦙 FlaStruct & FLARE Dataset

**Fine-grained Hate Speech Detection via Structured Generation**

[![Status: Under Review](https://img.shields.io/badge/Status-Under%20Double--Blind%20Review-blue.svg)](#) 
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#)

</div>

> ### 🚨 **ANONYMOUS SUBMISSION NOTICE**
> This repository is currently under **double-blind peer review**. To comply with anonymity policies, author affiliations and identifying details have been removed. 
> 
> 📢 **The complete training/inference source code, the pre-trained `FlaStruct` model weights, and the `FLARE` dataset will be FULLY OPEN-SOURCED immediately upon paper acceptance.**

---

## 💡 Overview

This repository hosts the code, model, and data for **FlaStruct**, a novel framework for fine-grained hate speech detection, and **FLARE**, a specialized Chinese financial community dataset. 

Instead of treating hate speech detection as a traditional binary classification task, **FlaStruct** fine-tunes Large Language Models (e.g., Llama-3.1) to generate **structured JSON outputs**, jointly identifying the presence of hate speech, its target group, and the attack type in a single inference step.

## 🚀 The Paradigm Shift

**❌ Traditional Vanilla-SFT:**
```json
{"label": "hate"}

```

**✅ FlaStruct (Ours):**

```json
{
  "label": "hate", 
  "target_group": "Financial Role", 
  "attack_type": "Stereotyping"
}

```

*(Built-in logical consistency: if `label` is `non-hate`, `target_group` and `attack_type` strictly default to neutral placeholders).*

## 📦 What Will Be Released?

Upon acceptance, this repository will provide full access to:

* **The FLARE Dataset**: A meticulously annotated dataset for fine-grained hate speech detection in Chinese financial domains.
* **FlaStruct Model Weights**: LoRA weights and merged model checkpoints based on `Meta-Llama-3.1-8B-Instruct`.
* **Core Codebase**: Clean, reproducible pipelines for data processing, SFT training, and structural JSON evaluation.

## 📂 Repository Skeleton

The codebase is streamlined for out-of-the-box usage. The full implementation will populate this structure post-acceptance:

```text
flastruct_open/
├── data/                  # 🔒 FLARE dataset & splits (To be released)
├── model/                 # 🔒 FlaStruct pre-trained weights & LoRA adapters
├── src/
│   ├── train/             # SFT training scripts & prompt builders
│   ├── inference/         # Batch inference & structured JSON generation
│   └── utils/             # Data loaders, JSON parsers, and evaluation metrics
├── requirements.txt       # Environment dependencies
└── README.md              # Documentation

```

## 📝 License

This project will be released under the [MIT License](https://www.google.com/search?q=LICENSE). Base models (e.g., Llama-3.1) and any third-party tools are subject to their respective original licenses.

```

```
