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

Four repositories compose into one pipeline: extract flow features, validate them,
evaluate honestly, then attack the result.

| Project | What it does |
| --- | --- |
| [**flowlens**](https://github.com/SohanBag/flowlens) | C++17 network flow feature extraction. Reads pcap and pcapng directly, holds constant memory per flow, stays bounded under floods that open millions of one-packet flows. **185,000 pkt/s**, and capping the flow table made it *faster* because the table stays cache-resident. |
| [**leakhunt**](https://github.com/SohanBag/leakhunt) | Finds data leakage and suspicious evaluation behaviour in ML pipelines. Validated on UCI HAR: a leaky protocol produced **36x tighter** confidence intervals, which is how you spot one. |
| [**featureguard**](https://github.com/SohanBag/featureguard) | Catches schema breaks, NaNs and distribution drift before they reach a model. Schema validation costs **2.2 us regardless of batch size**; streaming drift runs in 879 KiB where raw history would need 57 MB. |
| [**evade-nids**](https://github.com/SohanBag/evade-nids) | Leakage-free intrusion-detection benchmarking. On real CTU-13 botnet captures, holding out whole hosts instead of splitting flows at random cuts XGBoost macro F1 from 0.9456 to 0.8226, a **significant 12.3-point** inflation. Adversarial attacks are constrained to be physically sendable; unconstrained ones overstate evasion by **36 points**. |

A theme runs through them. Each one exists because something fails quietly: a column
order that changes without raising, a split that leaks, a NaN that propagates, an attack
that works on a feature vector no packet sequence could produce. The interesting bugs are
the ones that do not crash.

Three more come from the systems and accelerator side of the work:

| Project | What it does |
| --- | --- |
| [**spikekern**](https://github.com/SohanBag/spikekern) | Fused **Triton** kernels for spiking neuron dynamics. A LIF layer written the obvious way costs 1,280 kernel launches at `T=256`; fused, it costs two. **22x to 129x faster than snnTorch**, 22% less memory, with spike trains bit-identical and gradients matching to 2.9e-07. The first backward kernel was wrong by 0.94 relative while the forward was bit-exact, which is why it is checked against two independent implementations. |
| [**edgeflow**](https://github.com/SohanBag/edgeflow) | Takes a PyTorch model to INT8 and measures what it cost. Found that the standard activation-outlier heuristic ranks a **real** CNN's layers in near-reverse order of actual damage, having scored a perfect +1.000 on the synthetic fixtures. Also that INT8 ran **2.5x slower** than float32, which a report showing only compression would have called a win. |
| [**npudialect**](https://github.com/SohanBag/npudialect) | An out-of-tree **MLIR** dialect for an NPU with a software-managed scratchpad. Verifiers reject programs that are valid MLIR and wrong for the hardware, like compute reading DRAM instead of the scratchpad. Passes for elementwise fusion, budget-aware tile selection and DMA double buffering. |

[**spikefit**](https://github.com/SohanBag/spikefit) sits alongside spikekern, attacking the same problem from the memory side with gradient checkpointing over the temporal dimension: **86.8% less peak memory** and **10x the batch size** at `T=256`, with gradients bit-identical to standard BPTT. The two compose.

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
