# Create and Add to an Example Gallery for Toqito

## Abstract

This project aims to develop a comprehensive example gallery for Toqito, enhancing its accessibility to quantum information theory researchers. Following the scikit-learn examples page format, I will create a collection of standalone Python scripts demonstrating Toqito's capabilities across various use cases. The gallery will feature 5 detailed examples, including E91 quantum key distribution using the CHSH game, quantum bit commitment and its no-go theorem, state antidistinguishability with Pretty Good Measurement, entanglement detection with witness construction, and quantum channel effects. These examples will connect theoretical concepts to practical implementations, significantly lowering the barrier to entry for new users while showcasing Toqito's advanced capabilities in quantum information theory.

## Technical Details

Toqito is an open-source Python library for researchers in quantum information theory. While it offers powerful functionality, its adoption may be limited by the lack of comprehensive, practical examples that demonstrate its capabilities across various quantum information theory applications.

### Proposed Gallery Structure

The example gallery will follow the scikit-learn examples page structure (https://scikit-learn.org/stable/auto_examples/index.html), featuring:

1. A main gallery page with tiled thumbnails
2. Categorization by topic areas
3. Searchable examples
4. Clear navigation and consistent formatting

Each example will follow a standard format:
- Title and brief description
- Imports and setup
- Step-by-step implementation with explanatory comments
- Visualization where applicable
- References to academic literature
- Expected output

### Technical Requirements

- **Libraries**: Toqito, NumPy, SciPy, Matplotlib
- **Documentation**: Sphinx for generating gallery pages
- **Version Control**: Git/GitHub for collaboration
- **Testing**: pytest for ensuring example functionality
- **Visualization**: Matplotlib and other visualization libraries as needed

### Specific Examples to Implement

1. **Quantum Key Distribution using the CHSH Game (E91 Protocol)**
   - **Goal**: Demonstrate the role of quantum entanglement and nonlocality in enabling secure quantum key distribution
   - **Technical Implementation**: This example will simulate the E91 protocol [Ekert91], where Alice and Bob share entangled pairs and test Bell inequalities using the CHSH game. Using Toqito, we will define the CHSH game matrix, construct optimal quantum strategies, and compute the expected winning probability. We'll compare classical vs. quantum bounds (Tsirelson's bound) and show how violation of the Bell inequality guarantees security against eavesdropping.
   - **Code Components**:
     - Definition of the CHSH game matrix and probability distribution
     - Construction of shared entangled states (Bell states)
     - Implementation of optimal measurement strategies
     - Calculation of expected winning probabilities
     - Comparison of classical bound (0.75) vs. quantum bound (~0.85)
     - Security analysis based on Bell inequality violation
   - **Visualization**: Graphs showing Bell inequality violations and their relation to security guarantees
   - **References**:
     - Ekert, A. K. (1991). Quantum cryptography based on Bell's theorem. Phys. Rev. Lett., 67(6), 661.
     

2. **Quantum Bit Commitment and No-Go Theorem Demonstration**
   - **Goal**: Illustrate the impossibility of unconditionally secure bit commitment in quantum protocols (Mayers-Lo-Chau theorem)
   - **Technical Implementation**: We will construct a basic bit commitment protocol: Alice sends Bob a quantum state encoding a bit, which she reveals later. Using Toqito, we simulate cheating strategies such as state purification and fidelity optimization to show how Alice can change her bit after the commit phase. This example makes the Mayers-Lo-Chau impossibility theorem tangible.
   - **Code Components**:
     - Implementation of a basic quantum bit commitment protocol
     - Creation of commitment states for bit 0 and bit 1
     - Demonstration of an "honest" protocol execution
     - Implementation of cheating strategies using purification
     - Calculation of the success probability for changing the committed bit
     - Analysis showing that perfect binding and concealing cannot be achieved simultaneously
   - **Visualization**: Protocol diagrams, security parameter analysis, trade-off curves between binding and concealing properties
   - **References**:
     - Mayers, D. (1997). Unconditionally secure quantum bit commitment is impossible. Phys. Rev. Lett., 78, 3414.
     - Lo, H. K., & Chau, H. F. (1997). Is quantum bit commitment really possible?. Phys. Rev. Lett., 78, 3410.

3. **State Antidistinguishability and Pretty Good Measurement (PGM)**
   - **Goal**: Explore concepts of state (anti)distinguishability and implement Pretty Good Measurement (PGM) for quantum state discrimination
   - **Technical Implementation**: We'll define a set of non-orthogonal quantum states and determine if they are antidistinguishable using SDP-based techniques available in Toqito. The example will implement the PGM and calculate the success probabilities in distinguishing the states. This is an excellent educational illustration of both optimal measurement theory and its limitations.
   - **Code Components**:
     - Definition of sets of non-orthogonal quantum states from literature
     - Implementation of Pretty Good Measurement (PGM) using Toqito
     - Calculation of antidistinguishability probabilities
     - Comparison with optimal measurements and theoretical bounds
     - Analysis of success probabilities for different state sets
   - **Visualization**: success probability plots
   - **References**:
     - Caves, C. M., Fuchs, C. A., & Schack, R. (2002). Conditions for compatibility of quantum-state assignments. Phys. Rev. A 66, 062111.
     - Hausladen, P., & Wootters, W. K. (1994). A pretty good measurement for distinguishing quantum states. J. Mod. Opt. 41(12), 2385–2390.

4. **Entanglement Detection and Witness Construction**
   - **Goal**: Provide a practical method for detecting entanglement using the PPT criterion and constructing entanglement witnesses
   - **Technical Implementation**: We will generate both separable and entangled bipartite states (e.g., Bell states, Werner states). Using Toqito's partial_transpose module, we will apply the Peres-Horodecki criterion. We will then construct an entanglement witness using Toqito's optimization methods and verify its effectiveness via inner product evaluations.
   - **Code Components**:
     - Generation of various bipartite quantum states (Bell states, Werner states)
     - Implementation of the Peres-Horodecki (PPT) criterion using partial_transpose
     - Construction of entanglement witnesses using optimization techniques
     - Verification of witness effectiveness through inner product calculations
     - Analysis of the boundary between separable and entangled states
   - **Visualization**: 2D scatter plot of witness values, expectation value bar chart, etc.
   - **References**:
     - Peres, A. (1996). Separability criterion for density matrices. Phys. Rev. Lett., 77, 1413.
     - Horodecki, M., Horodecki, P., & Horodecki, R. (1996). Separability of mixed states: Necessary and sufficient conditions. Phys. Lett. A, 223(1-2), 1–8.
     - Gühne, O., & Tóth, G. (2009). Entanglement detection. Phys. Rep., 474(1-6), 1–75.

5. **Quantum Channel Effects: Depolarizing and Amplitude Damping Channels**
   - **Goal**: Quantify the effect of quantum noise using common channels and metrics like fidelity and entanglement fidelity
   - **Technical Implementation**: We'll define depolarizing and amplitude damping channels and apply them to maximally entangled states and single-qubit pure states. Toqito will be used to apply Kraus maps and calculate how the fidelity degrades under these noisy processes. This example will also plot fidelity decay and visually demonstrate decoherence.
   - **Code Components**:
     - Definition of depolarizing and amplitude damping channels using Kraus operators
     - Application of these channels to various quantum states
     - Calculation of fidelity and entanglement fidelity before and after channel application
     - Analysis of fidelity decay as a function of noise parameters
     - Comparison of different noise models and their effects
   - **Visualization**: fidelity decay plots, matrix heatmap comparison.
   - **References**:
     - Nielsen, M. A., & Chuang, I. L. (2010). Quantum Computation and Quantum Information. Cambridge University Press. (Chapters on Quantum Channels)
     - Schumacher, B. (1996). Sending entanglement through noisy quantum channels. Phys. Rev. A 54, 2614.

### Exploration of Existing Codebase

I have examined the current Toqito codebase, particularly focusing on:
- The module structure and API design
- Existing examples and documentation
- Implementation of quantum information primitives
- Testing framework

Based on this exploration, I have identified several areas where comprehensive examples would be particularly beneficial and how these examples could be integrated with the existing codebase.

## Schedule of Deliverables

### **Community Bonding Period** (3 weeks)
- Week 1: Set up development environment, familiarize with Toqito codebase in detail
- Week 2: Study scikit-learn's gallery implementation, draft example template and style guide
- Week 3: Create detailed specifications for each example, finalize project plan with mentors
- Deliverables:
  * Development environment setup report
  * Example template and style guide document
  * Detailed project plan with timeline
  * Initial blog post introducing the project

### **Phase 1** (4 weeks)
- Week 1: Implement gallery framework structure and navigation
- Week 2: Develop Example 1 (Quantum Key Distribution using the CHSH Game)
- Week 3: Develop Example 2 (Quantum Bit Commitment and No-Go Theorem)
- Week 4: Testing, documentation, and code review for Examples 1-2
- Deliverables:
  * Working gallery framework with navigation
  * Completed Examples 1-2 with documentation
  * Comprehensive tests for Examples 1-2
  * Phase 1 blog post documenting progress and challenges

### **Phase 2** (4 weeks)
- Week 1: Develop Example 3 (State Antidistinguishability and PGM)
- Week 2: Develop Example 4 (Entanglement Detection and Witness Construction)
- Week 3: Develop Example 5 (Quantum Channel Effects)
- Week 4: Testing, documentation, and code review for Examples 3-5
- Deliverables:
  * Completed Examples 3-5 with documentation
  * Comprehensive tests for Examples 3-5
  * Updated gallery with all examples integrated
  * Phase 2 blog post showcasing examples and their applications

### **Final Phase** (4 Weeks)
- Final polish and integration of all examples
- Comprehensive testing across different environments
- Complete all documentation
- Submit final code and prepare for merge
- Deliverables:
  * Fully functional example gallery with 5 comprehensive examples
  * Complete documentation and tests
  * Final blog post summarizing project achievements
  * Pull request ready for review and merge

## Development Experience
- **Github**: https://github.com/Vanshaj0429

I have experience working with Python and scientific computing libraries from various projects:

1. **QOSF (Quantum Open Source Foundation) Mentorship Program (Cohort 10) - Screening Phase**: During the screening phase, I developed a quantum state-vector simulator using matrix and tensor-based approaches to simulate quantum circuits, perform runtime analysis, and conduct scalability testing. https://github.com/Vanshaj0429/Quantum-Statevector-Simulator 

2. **QOSF (Quantum Open Source Foundation) Mentorship Program (Cohort 10) - Project Phase**: Currently, I am working on a project involving time evolution algorithms in the Pauli basis, specifically the Pauli propagation technique using Julia. Through this project, I am comparing different numerical methods within a simulation framework to identify the most efficient approach. 

3. **Condensed Matter Research at Cardiff University**: Used QuTiP to model quantum electrodynamics systems, particularly focusing on the Jaynes-Cummings model and dissipative processes. I developed a simulation framework that analysed both coherent and dissipative processes in the system. Also created custom functions for JC Hamiltonian which can be used for analysis with different parameters easily, in short improved utlity. https://github.com/Vanshaj0429/cavity-qed-simulations

4. **MSc Thesis on Holographic Quantum Error Correction**: I developed a github repository with project plan and thesis to showcase my work. https://github.com/Vanshaj0429/MSc_Thesis_HolographicQEC

5. **Classiq Paper Implementation Challenge**: My proposal has been selected for paper implementation challenege. https://github.com/Classiq/classiq-library/issues/825



## Other Experiences

1. **Quantum Computing Education**: Completed a comprehensive two-semester course with a score of 96%, covering quantum mechanics, quantum information theory, and hands-on programming with quantum computing frameworks.

2. **Summer Schools**: Participated in the IQOQI Summer School on quantum optics and information science and the VCQ & TURIS Summer School on interfacing gravity and quantum physics, demonstrating my commitment to continuous learning in quantum information theory.

3. **Academic Excellence**: Received the Cardiff University India Scholarship for academic excellence, and achieved a Distinction in my MSc Physics program, with particular strength in quantum theory courses.


## Why this project?

I am drawn to this project for three main reasons:

First, it perfectly aligns with my background in quantum information theory and my passion for making complex concepts accessible. Having navigated the learning curve of quantum computing libraries myself, I understand the value of comprehensive examples that bridge theory and implementation.

Second, I believe in the importance of open-source tools for advancing quantum information research. By creating a comprehensive example gallery, I can contribute to making Toqito more accessible to researchers and students, potentially accelerating discoveries in the field.

Finally, the project offers an excellent opportunity to deepen my understanding of quantum information theory while developing practical programming skills. Working on examples that span from quantum key distribution to quantum state optimization will help me build a more comprehensive understanding of the field's applications.

The idea of creating resources that researchers around the world might use to advance quantum information theory is deeply motivating to me, and I am excited about the opportunity to contribute to Toqito's development in this way.

## Appendix

### Additional Reference Resources
1. Nielsen, M. A., & Chuang, I. L. (2010). Quantum computation and quantum information. Cambridge University Press.
2. Watrous, J. (2018). The theory of quantum information. Cambridge University Press.
3. Wilde, M. M. (2013). Quantum information theory. Cambridge University Press.

### Example Gallery Inspiration
Beyond scikit-learn, I've examined example galleries from:
- QuTiP (https://qutip.org/tutorials.html)
- Qiskit (https://qiskit.org/documentation/tutorials.html)
- Pennylane (https://pennylane.ai/qml/demonstrations.html)

Each offers valuable insights into effective example presentation for quantum computing tools, which I will incorporate into my approach.

## Personal Details

- **Name**: Vanshaj Bindal
- **Education**: MSc Physics, Cardiff University, UK
- **Research Interest**: Quantum Inforamtion Theory, Quantum Simulation, Quantum Error Correction, Tensor Netowrks, Quantum Many Body Physics, Holography.
- **Linkedin Profile**: https://www.linkedin.com/in/vanshaj-bindal-487953244/ 
- **Github Profile**: https://github.com/Vanshaj0429

