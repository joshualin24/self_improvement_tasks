# Self-Improvement Tasks

---

## Biology

- [ ] Read and summarize one landmark paper per week (structural biology, immunology, or molecular evolution)
- [ ] Understand the central dogma end-to-end: DNA → RNA → protein → function → phenotype
- [ ] Learn antibody biology deeply: V(D)J recombination, affinity maturation, CDR loops, Fc effector functions
- [ ] Study protein structure: secondary structure, fold families, Ramachandran plots, binding interfaces
- [ ] Understand assay readouts used in drug discovery: SPR, BLI, HTRF, yeast/phage display, deep mutational scanning
- [ ] Be able to read a clinical trial protocol and understand what the endpoints mean biologically
- [ ] Learn one model organism (mouse, zebrafish, or C. elegans) well enough to design an in vivo experiment

---

## Physics

- [ ] Rederive statistical mechanics from scratch: partition functions, free energy, entropy, Boltzmann distribution
- [ ] Understand thermodynamics of binding: ΔG = ΔH − TΔS, enthalpy-entropy compensation, Kd from first principles
- [ ] Learn electrostatics in biomolecules: Poisson-Boltzmann, Debye screening, charge-charge interactions at interfaces
- [ ] Study molecular dynamics: force fields, integration schemes, NPT/NVT ensembles, convergence
- [ ] Understand diffraction and cryo-EM: how atomic coordinates are actually determined from experimental data
- [ ] Work through one quantum chemistry textbook chapter (Hartree-Fock, DFT) to understand where force fields come from
- [ ] Be able to estimate an order of magnitude for: kT at 300K, a hydrogen bond energy, a van der Waals radius, a diffusion coefficient

---

## ML

Goals are structured around **protein sequences** as the learning substrate.

### PLM / LLM Pretraining
- [x] Implement a transformer from scratch (attention, positional encoding, layer norm) and pretrain on a small protein sequence corpus
- [x] Reproduce masked language modelling (BERT-style) on AIRR dataset sequences at small scale; verify perplexity decreases sensibly
- [ ] Understand ESM-2 architecture choices: why tied embeddings, why no absolute positional encoding, what the contact head does
- [ ] Train a PLM on multiple GPUs: implement data parallelism (DDP), understand gradient synchronisation, mixed precision (bf16/fp16), and gradient checkpointing to fit larger models in memory
- [ ] Implement next-token autoregressive pretraining on protein sequences (GPT-style) and compare representations to masked LM

### Post-Training
- [ ] Fine-tune a frozen PLM head on a labelled property (thermostability, binding affinity, solubility) using LoRA
- [ ] Implement supervised fine-tuning (SFT) on a curated set of high-affinity antibody sequences; measure held-out rank correlation
- [ ] Compare full fine-tuning vs. LoRA vs. adapter vs. frozen-backbone + MLP head on a fixed dataset; understand the data-regime tradeoffs
- [ ] Implement DPO or preference learning on pairs of protein sequences ranked by experimental affinity

### RL Fine-Tuning
- [ ] Frame CDR-H3 optimisation as an RL problem: state = current sequence, action = point mutation, reward = PLM log-likelihood or oracle score
- [ ] Implement REINFORCE on a toy protein design task; observe reward hacking and mode collapse firsthand
- [ ] Study PPO and implement it against a differentiable affinity oracle; compare sample efficiency to genetic algorithms
- [ ] Implement RLHF-style pipeline for protein sequences: pretrain PLM → SFT on good binders → train reward model → PPO against it
- [ ] Explore constrained RL: add penalties for edit distance from the lead, developability flags, or sequence diversity to prevent exploitation
