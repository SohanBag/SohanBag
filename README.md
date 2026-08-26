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

Four repositories, and they compose into one pipeline: extract flow features, validate
them, evaluate honestly, then attack the result.

| Project | What it does |
| --- | --- |
| [**flowlens**](https://github.com/SohanBag/flowlens) | C++17 network flow feature extraction. Reads pcap directly, holds constant memory per flow, stays bounded under floods that open millions of one-packet flows. **185,000 pkt/s**, and capping the flow table made it *faster* because the table stays cache-resident. |
| [**leakhunt**](https://github.com/SohanBag/leakhunt) | Finds data leakage and suspicious evaluation behaviour in ML pipelines. Validated on UCI HAR: a leaky protocol produced **36x tighter** confidence intervals, which is how you spot one. |
| [**featureguard**](https://github.com/SohanBag/featureguard) | Catches schema breaks, NaNs and distribution drift before they reach a model. Schema validation costs **2.2 us regardless of batch size**; streaming drift runs in 879 KiB where raw history would need 57 MB. |
| [**evade-nids**](https://github.com/SohanBag/evade-nids) | Leakage-free intrusion-detection benchmarking. A random split reports 0.999 F1 where holding out whole capture sessions gives 0.169. Adversarial attacks are constrained to be physically sendable; unconstrained ones overstate evasion by **36 points**. |

A theme runs through them. Each one exists because something fails quietly: a column
order that changes without raising, a split that leaks, a NaN that propagates, an attack
that works on a feature vector no packet sequence could produce. The interesting bugs are
the ones that do not crash.

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
