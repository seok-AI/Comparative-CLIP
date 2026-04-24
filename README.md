# Comparative-CLIP — [WACV 2025]

**Enhancing Visual Classification using Comparative Descriptors**
H. Lee, G. Seo, **W. Choi**, G. Jung, K. Song, J. Jung
*IEEE/CVF Winter Conference on Applications of Computer Vision (WACV), 2025*

> 📌 **About this fork.** This repository is the co-maintained mirror of the official code.
> Upstream: [`hankyeol/Comparative-CLIP`](https://github.com/hankyeol/Comparative-CLIP).
> Both repositories are canonical; issues and PRs are welcome on either.

---

## ✨ TL;DR

We generate **structured comparative descriptors** with an LLM, then use them to steer CLIP's zero-shot classification behavior in a measurable, reproducible way. The paper is, in effect, a prompt-engineering study validated on vision-language benchmarks.

## 🧑‍🔬 My contribution

- Descriptor-generation pipeline over LLM APIs — prompt schema design, structured (JSON) output parsing, retry / rate-limit handling, prompt versioning.
- Large-scale CLIP inference benchmarking — {N} descriptor variants × {M} datasets, logged in W&B.
- Ablations on {specific axis you owned, e.g., descriptor granularity / comparison pair sampling}.

## 🧪 Reproduce

```bash
git clone https://github.com/seok-AI/Comparative-CLIP.git
cd Comparative-CLIP
conda env create -f environment.yml && conda activate ccclip
# 1. Generate descriptors (requires OPENAI_API_KEY)
python scripts/generate_descriptors.py --config configs/imagenet.yaml
# 2. Evaluate on benchmarks
python scripts/eval_clip.py --descriptors outputs/imagenet.json
```

## 📈 Results

{Copy the main table from the paper — dataset × method × metric.}

## 📂 Layout

```
configs/      # per-dataset YAML
prompts/      # versioned descriptor-generation prompts
src/          # descriptor gen, CLIP eval, metrics
scripts/      # entry points
```

## 📝 Citation

```bibtex
@inproceedings{lee2025comparative,
  title     = {Enhancing Visual Classification using Comparative Descriptors},
  author    = {Lee, Hankyeol and Seo, Gwanghyun and Choi, Wonseok and Jung, Gwangho and Song, Kyungwoo and Jung, Jiyoung},
  booktitle = {IEEE/CVF Winter Conference on Applications of Computer Vision (WACV)},
  year      = {2025}
}
```

## 📜 License

Follows the upstream repository's license.
