# Chain-of-Thought Hijacking

This repository contains the reference implementation for **Chain-of-Thought Hijacking**, a jailbreak technique that exploits extended reasoning to weaken refusal behaviour in large reasoning models.

📄 Paper: https://arxiv.org/abs/2510.26418  
🌐 Project Page: https://gentlyzhao.github.io/Hijacking/  
💻 Authors: Jianli Zhao, Tingchen Fu, Rylan Schaeffer, Mrinank Sharma, and Fazl Barez

---

## 🚨 Purpose & Responsible Use

This code is released **for defensive research and model robustness evaluation only.**  
It is intended to help researchers and developers:

- Detect when long chain-of-thought reduces safety behaviour  
- Stress-test refusal stability across models  
- Develop mitigations for reasoning-driven jailbreaks  

**Do not use this method to cause harm.**  
We disclosed this vulnerability to multiple major AI labs in advance of publication.

---

## 🔧 Installation

```bash
git clone https://github.com/gentlyzhao/Hijacking.git
cd Hijacking
pip install -r requirements.txt
export GEMINI_API_KEY="..."      # Required (used for judge + attacker prompting)
export OPENAI_API_KEY="..."      # For GPT models
export ANTHROPIC_API_KEY="..."   # For Claude models
export GROK_API_KEY="..."        # For xAI models
```

## Basic Usage
Attack a single model
```
python main.py --target-model claude-4-sonnet
```
## Evaluate a slice of HarmBench
```
python main.py \
  --target-model gpt-o4-mini \
  --start-examples 1 \
  --end-examples 100
```

## Test a single custom goal
```
python main.py --goal "YOUR_GOAL_DESCRIPTION"
```

## 🔧 Offline Testing Mode (No API Key Required)

Generate adversarial prompts without API calls for manual testing:

```bash
# Generate prompts for a specific goal
python offline_test.py --goal "YOUR_TEST_GOAL"

# Generate only a specific stream (1-2)
python offline_test.py --goal "YOUR_TEST_GOAL" --stream 1

# Different output formats
python offline_test.py --goal "YOUR_TEST_GOAL" --output-format markdown
python offline_test.py --goal "YOUR_TEST_GOAL" --output-format prompts-only
```

This mode generates copy-pasteable prompts that you can test manually on:
- Claude.ai (Projects with custom system prompts)
- OpenAI Playground
- Anthropic API Console
- Any LLM interface that supports system prompts

**No API keys needed** - perfect for quick testing and experimentation!

❤️ Acknowledgments

This implementation builds on PAIR (Prompt Automatic Iterative Refinement) by Patrick Chao et al.
We thank the Oxford Martin AI Governance Initiative for research support.

```bibtex
@article{zhao2025hijacking,
  title={Chain-of-Thought Hijacking},
  author={Zhao, Jianli and Fu, Tingchen and Schaeffer, Rylan and Sharma, Mrinank and Barez, Fazl},
  year={2025},
  journal={arXiv preprint arXiv:2510.26418}
}
