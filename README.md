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

### Quantum Learning Theory (Caltech Ph 220 — Hsin-Yuan Huang)
Reference: https://caltech-quantum-learning-theory.github.io

#### Foundations & Quantum Many-Body Review
- [ ] Magnetic field sensing with spin sensors: derive the standard quantum limit and Heisenberg limit; understand why entanglement gives a 1/N vs 1/√N scaling advantage
- [ ] Review local Hamiltonians, ground states, Gibbs states, and tensor networks; implement Matrix Product State (MPS) contraction and simulate measurements on a 1D chain
- [ ] Understand why 1D/2D states can be classically simulated via MPS; know the complexity class separation PostBPP ≠ PostBQP and what it implies for quantum advantage

#### Random Unitaries & Weingarten Calculus
- [ ] Understand Haar-random unitaries: what they are, how to sample them, and why they matter for quantum information
- [ ] Work through Schur-Weyl duality and Weingarten calculus: compute 2nd and 4th moment operators over the unitary group
- [ ] Understand t-designs: what it means for a finite ensemble to reproduce the first t moments of the Haar measure; construct a 2-design from random Clifford circuits
- [ ] Study the path-recording oracle technique for proving lower bounds on quantum learning algorithms

#### Quantum State Tomography & Shadow Tomography
- [ ] Implement randomized measurement schemes: apply a random unitary, measure in the computational basis, and reconstruct the classical shadow of a state
- [ ] Derive the classical shadow protocol using random Clifford circuits: shadow channel, median-of-means estimator, sample complexity O(log M / ε²) for M observables
- [ ] Prove sample-optimal tomography: understand why Ω(d²) copies are needed for full tomography and how pretty good measurements achieve it
- [ ] Study the Gentle Measurement Lemma and Quantum Union Bound; apply them in the Quantum Threshold Search algorithm
- [ ] Work through Full Shadow Tomography: predict M observables on an unknown state to ε accuracy using only O(log M · poly(1/ε)) copies — understand why this is exponentially better than naive tomography

#### Online Learning & Multiplicative Weights in the Quantum Setting
- [ ] Master the classical "prediction with experts" framework: Follow the Regularized Leader (FTRL), Multiplicative Weight Update (MWU), regret bounds O(√T log N)
- [ ] Extend MWU to the quantum domain (Matrix MWU): replace probability vectors with density matrices, scalar weights with positive semidefinite operators
- [ ] Reproduce the Full Shadow Tomography result using Matrix MWU as the core subroutine; verify sample complexity

#### Quantum Neural Networks
- [ ] Understand barren plateaus: prove that for a random deep quantum circuit the gradient of any observable vanishes exponentially in system size
- [ ] Study parameterization by local inversion and "sewing" local inversions to reconstruct a full circuit — understand how this avoids barren plateaus
- [ ] Understand generative quantum advantage: what class of distributions can a quantum circuit sample from that a classical circuit cannot? Work through one formal separation

#### Hamiltonian Learning & Noise Characterization
- [ ] Study Gate Set Tomography: why standard process tomography is gauge-dependent; how GST simultaneously characterises gates, state preparation, and measurement
- [ ] Understand noise twirling to Pauli channels: twirl an arbitrary noise channel over the Clifford group to produce a Pauli channel; derive the twirled channel analytically
- [ ] Work through Heisenberg-limited Hamiltonian learning: understand the reshaping technique that achieves 1/ε scaling in total evolution time rather than 1/ε²

#### Pseudorandomness in Quantum Computing
- [ ] Study Pseudorandom States (PRS): define them, construct a PRS family from a pseudorandom function, and prove they are computationally indistinguishable from Haar-random states by any polynomial-time quantum algorithm
- [ ] Work through the trace distance analysis: why exponentially many copies are needed to statistically distinguish a PRS from Haar-random
- [ ] Study Pseudorandom Unitaries (PRU): understand the existence proof using tools from random unitaries, post-quantum cryptography (one-way functions), and purification arguments

#### Quantum Advantage in Learning
- [ ] Prove the exponential quantum advantage for learning Pauli observables: show that a classical agent requires exponentially many experiments while a quantum agent (using entangled measurements across copies) requires only polynomially many
- [ ] Work through the learning tree formalism: model classical/quantum learning algorithms as trees, define depth and width, and use it to prove lower bounds on classical sample complexity
- [ ] Study quantum PCA: understand how a quantum computer can extract principal components of an unknown density matrix exponentially faster than classical algorithms (and also understand the dequantisation results that narrow the gap)
- [ ] Explore Quantum × AI frontiers: AI for quantum error correction, autonomous discovery of quantum protocols, and using quantum computers to accelerate ML training

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
- [ ] AlphaGo-style fine-tuning for B cell somatic hypermutation: train a policy network that proposes point mutations and a value network that estimates downstream affinity gain, then use MCTS over the CDR sequence space guided by both networks
