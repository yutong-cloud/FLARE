<div align="center">

#  FLARE

**Fine-grained Hate Speech Detection via Structured Generation**

[![Status: Under Review](https://img.shields.io/badge/Status-Under%20Double--Blind%20Review-blue.svg)](#) 
[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#)

</div>

> ### ⚠️ **ANONYMOUS SUBMISSION NOTICE**
> This repository is currently under **double-blind peer review**. To comply with anonymity policies, author affiliations and identifying details have been removed. 
> 
> 📢 **The complete source code, training/evaluation scripts, pre-trained model weights, and the newly constructed Chinese Financial Hate Speech Dataset will be FULLY OPEN-SOURCED immediately upon paper acceptance.**

---

## 💡 Overview

**Struct-Llama** introduces a paradigm shift in hate speech detection within Chinese financial communities. Instead of treating the problem as a traditional binary classification task, we fine-tune Large Language Models (e.g., Llama-3.1) via SFT to generate **structured JSON outputs**, jointly identifying the presence of hate speech, its target group, and the attack type.

## 🚀 The Paradigm Shift

**❌ Traditional Vanilla-SFT:**
```json
{"label": "hate"}
✅ Struct-Llama (Ours):

JSON
{
  "label": "hate", 
  "target_group": "Financial Role", 
  "attack_type": "Stereotyping"
}
(Built-in logical consistency: if label is non-hate, target_group and attack_type strictly default to neutral placeholders).

✨ Key Highlights
🎯 Multi-dimensional Extraction: Simultaneously predicts Label, Target Group, and Attack Type.

🧩 Structured Constraint: Ensures parsable, rule-compliant JSON generation for downstream pipeline integration.

🛡️ Superior Robustness: Outperforms baseline models in in-domain detection, cross-domain generalization (ToxiCN), and adversarial testing.

🔬 Analytical Depth: Enables advanced linguistic analyses, including implicit metaphor detection and demographic-attack heatmaps.

📂 Repository Skeleton
The codebase is highly modularized for reproducibility. The full implementation will populate this structure post-acceptance:

Plaintext
struct_llama/
├── data/                  # 🔒 Dataset & splits (To be released)
├── src/
│   └── conll_flare/
│       ├── exp1_main/         # Core SFT training & inference pipeline
│       ├── exp2_generalization/# Cross-domain (ToxiCN) evaluation
│       ├── exp3_linguistic/   # Metaphor & heatmap analysis
│       ├── exp4_ablation/     # Ablation studies
│       ├── exp5_adversarial/  # Adversarial robustness testing
│       └── utils/             # Data loaders, JSON parsers, metrics
├── requirements.txt       # Dependencies
└── README.md              # Documentation
📝 License
This project will be released under the MIT License. Base models and third-party datasets are subject to their respective original licenses.
