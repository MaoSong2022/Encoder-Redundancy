# Investigating Redundancy in Multimodal Large Language Models with Multiple Vision Encoders

**ICLR 2026**

[![Project Page](https://img.shields.io/badge/Project_Page-encoder--redundancy.github.io-blue)](https://encoder-redundancy.github.io/)
[![arXiv](https://img.shields.io/badge/arXiv-2507.03262-b31b1b)](https://arxiv.org/abs/2507.03262)
[![OpenReview](https://img.shields.io/badge/OpenReview-Forum-green)](https://openreview.net/forum?id=cAopJVLKvi)
[![Hugging Face](https://img.shields.io/badge/🤗_Models-Encoder--Redundancy-yellow)](https://huggingface.co/collections/DiDisama/finetuned-eagle-models)

**Authors:** Yizhou Wang\*, Song Mao\*, Yang Chen\*, Yufan Shen, Yinqiao Yan, Pinlong Cai, Ding Wang, Guohang Yan, Zhi Yu, Xuming Hu, Botian Shi  
**Affiliation:** Shanghai AI Lab, HKUST(GZ), Zhejiang University, Beijing University of Technology  
*\*Equal contribution. † Work done during internship at Shanghai AI Lab.*

---

## Abstract

Recent multimodal large language models (MLLMs) increasingly integrate multiple vision encoders to improve performance on various benchmarks, assuming that diverse pretraining objectives yield complementary visual signals. However, we show this assumption often fails in practice. Through systematic encoder masking across representative multi-encoder MLLMs, we find that **performance typically degrades gracefully—and sometimes even improves—** when selected encoders are masked, revealing **pervasive encoder redundancy**.

To quantify this effect, we introduce two principled metrics:

- **Conditional Utilization Rate (CUR)** — measures an encoder’s marginal contribution in the presence of others.
- **Information Gap (IG)** — captures heterogeneity in encoder utility within a model.

Using these tools, we observe: (i) strong specialization on tasks like **OCR & Chart**, where a single encoder can dominate (CUR >90%); (ii) **high redundancy** on general VQA and knowledge-based tasks, where encoders are largely interchangeable; (iii) instances of **detrimental encoders** with negative CUR. Notably, masking specific encoders can yield up to **16%** higher accuracy on a task category and **3.6%** overall performance boost compared to the full model.

Furthermore, **single- and dual-encoder variants recover over 90% of baseline** on most non-OCR tasks with substantially lower training resources and inference latency. Our analysis challenges the “more encoders are better” heuristic and provides actionable diagnostics for developing more efficient multimodal architectures.

---

## Project Page & Resources

| Resource | Link |
|----------|------|
| **Project page** (paper, figures, case studies, results) | [encoder-redundancy.github.io](https://encoder-redundancy.github.io/) |
| **arXiv** | [arxiv.org/abs/2507.03262](https://arxiv.org/abs/2507.03262) |
| **OpenReview** | [openreview.net/forum?id=cAopJVLKvi](https://openreview.net/forum?id=cAopJVLKvi) |
| **Code** | [github.com/Encoder-Redundancy/Encoder-Redundancy](https://github.com/1zhou-Wang/Investigating_MultiEncoder_Redundancy) |
| **Models** | [huggingface.co/Encoder-Redundancy](https://huggingface.co/collections/DiDisama/finetuned-eagle-models) |

The project page (`index.html`) includes:

- Teaser and motivation
- Case studies (encoder masking effects)
- Method (CUR, IG, architectures, benchmarks)
- Key results (redundancy analysis, re-trained vs. original, efficiency)
- BibTeX citation

---

## Key Results (Summary)

1. **Pervasive encoder redundancy** — Across Eagle, Cambrian-1, I-MoF, Eagle2, DeepSeek-VL, performance degrades gracefully (or improves) when encoders are masked.
2. **Efficiency** — For Eagle-X5 7B, a dual-encoder variant (Eagle-X2 7B) reaches **94%** of full model performance with **~34%** training time reduction; masking three encoders at inference reduces latency by **19.5%** with &lt;4% performance drop.
3. **Dual-encoder variants** — Consistently recover **&gt;90%** of baseline on most non-OCR tasks with lower training and inference cost.

---

## Repository Structure

- `index.html` — Project page (paper description, figures, method, results).
- `static/` — CSS, JS, images, and PDFs used by the project page.

---

## Citation

If you find this work useful, please cite:

```bibtex
@inproceedings{wang2026investigating,
  title     = {Investigating Redundancy in Multimodal Large Language Models with Multiple Vision Encoders},
  author    = {Wang, Yizhou and Mao, Song and Chen, Yang and Shen, Yufan and Yan, Yinqiao and Cai, Pinlong and Wang, Ding and Yan, Guohang and Yu, Zhi and Hu, Xuming and Shi, Botian},
  booktitle = {International Conference on Learning Representations (ICLR)},
  year      = {2026}
}
```

---

## Acknowledgments

The project page is based on the [Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template). Parts were adopted from [Nerfies](https://nerfies.github.io/).

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).
