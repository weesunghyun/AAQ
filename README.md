# AAQ: Alignment-Aware Quantization for LLM Safety

Official code for the paper:

[[Paper (Coming Soon)]()]  
[[Project Page (TBA)]()]  
[[License](./LICENSE)]

---

## 🧠 Overview

Standard post-training quantization (PTQ) has emerged as a critical security vulnerability. Malicious actors can distribute seemingly safe models that are intentionally designed to become harmful only after an end-user applies standard quantization. This turns PTQ into an attack vector for activating hidden trojan behaviors, a threat known as alignment degradation.

In response, we propose Alignment-Aware Quantization (AAQ), the first defense mechanism integrated directly into the PTQ framework to neutralize this threat. AAQ reframes the quantization objective from simple reconstruction to active alignment preservation.

Our method uses a novel contrastive KL loss to act as a defensive guardrail:

- It steers the quantized model's behavior towards the safe, aligned model (the positive target).
- It actively pushes the model's behavior away from the unsafe, pre-trained base model (the negative reference).
- It serves as a lightweight and data-efficient defense that integrates seamlessly into existing PTQ pipelines using only unlabeled calibration data.

Tested on the LLaMA family (LLaMA2-Chat, LLaMA3-Instruct, etc.), AAQ successfully preserves safety alignment under 4-bit quantization, validating its effectiveness as a practical defense against malicious alignment degradation.

---

## 📦 Installation

```bash
git clone https://github.com/weesunghyun/AAQ.git
cd AAQ
conda create -n aaq python=3.10
conda activate aaq
pip install -r requirements.txt
```


## Citation
If you find OSTQuant useful in your research, please consider citing our paper:
```bibtex
@misc{wee2025aaq,
  title={Alignment-Aware Quantization for LLM Safety},
  author={Sunghyun Wee and Juhwan Cho and Seoyeon Park and Nojun Kwak},
  year={2025},
  note={arXiv:xxxx.xxxxx},
  url={https://github.com/weesunghyun/AAQ}
}
```
