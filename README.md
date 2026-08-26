# Sohan Bag

PhD researcher in Computer Science & Information Engineering at NTUST, Taipei.

I work on two things that turn out to be the same thing. One is spiking neural networks
for age-fair dementia detection from EEG and MRI. The other is machine learning inside
programmable network data planes. Both are about getting a model to behave under real
constraints, and both taught me that the interesting failures are the quiet ones: the
result that looks great because the split was wrong, the pipeline that degrades to chance
without raising an exception.

So most of what I build publicly is about catching that class of problem.

## What I'm working on

| Project | What it does |
| --- | --- |
| [**leakhunt**](https://github.com/SohanBag/leakhunt) | Finds data leakage and suspicious evaluation behaviour in ML pipelines. Model-free checks for CI, plus a diagnostic that measures what a leaky split is actually worth. Validated on UCI HAR: up to **36× tighter** confidence intervals under a leaky protocol, which is how you spot one. |

Currently building `flowlens`, a C++17 network flow feature extractor, and a reproducible
cross-dataset benchmark for ML-based intrusion detection.

## Background

- **PhD, CSIE, NTUST** (2025 to present). Neuromorphic and brain-inspired computing.
  Spiking neural networks conditioned on age, for dementia detection from EEG and MRI.
- **MSc, CSIE, NTUST** (2025). Hybrid P4 data-plane filtering with a searched DNN for
  DDoS detection in software-defined networks.
- **BTech, CSE, KIIT** (2023).

## Things I use

Python, C/C++, PyTorch, snnTorch, MNE-Python, scikit-learn, P4, BMv2, Mininet, Ryu, Linux.

## Contact

Taipei, Taiwan
[sohanbag00@gmail.com](mailto:sohanbag00@gmail.com)
[LinkedIn](https://www.linkedin.com/in/sohanbag)
