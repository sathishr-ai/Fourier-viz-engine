<div align="center">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3" />
  
  <br />
  <br />

  <h1 align="center">Animation of Fourier Series Convergence</h1>

  <p align="center">
    <strong>A high-performance, mathematically rigorous interactive visualization engine.</strong>
  </p>
  
  <p align="center">
    <a href="https://sathishr-ai.github.io/Fourier-viz-engine/">
      <img src="https://img.shields.io/badge/⚡_Live_Demo_Available_Here-2ea44f?style=for-the-badge&logo=github&logoColor=white" alt="Live Demo" />
    </a>
  </p>
  <br />

  <p align="center">
    <a href="#about-the-project">About</a> •
    <a href="#mathematical-architecture">Architecture</a> •
    <a href="#core-features">Features</a> •
    <a href="#technical-implementation">Implementation</a>
  </p>
</div>

---

## 🔬 About The Project

The **Fourier Series Visualization Engine** is a heavily optimized, client-side web application designed to mathematically dismantle and visualize the Superposition Principle. 

By bypassing traditional numerical integrations (which often suffer from catastrophic cancellation or floating-point bloat), this platform uses strict, purely analytical derivations of $a_n$ and $b_n$ Fourier coefficients to render exact geometric wave states. 

It is designed primarily as an academic mechanism to visibly demonstrate the **Gibbs Phenomenon** (the ringing artifacts that occur near jump discontinuities) and physically map statistical error bounds dynamically against an advancing harmonic limit scaler.

---

## ⚡ Core Features

### 1. Dynamic Superposition Rendering
At the heart of the engine is the `$FourierRenderer` class, operating natively at 60 Frames Per Second via `requestAnimationFrame`. As users dictate an upper harmonic bound `N` (up to 50 iterations), the engine mathematically superimposes pure sine and cosine arrays derived directly from the fundamental frequency limits.

### 2. Isolated Harmonic Decomposition Grid
Understanding Fourier math requires isolating the variables. By leveraging a custom additive DOM grid generation script, the engine physically generates 50 independent `<canvas>` instances dynamically. Each independent canvas maps to exactly one harmonic vector derived from the wave formula, exposing how individual sinusoidal amplitudes interact.

### 3. Real-Time Analytics & Error Bounding
Includes a proprietary `getErrors()` analytic module which scans 200 spatial points from $-\pi$ to $\pi$ in real time. 
* Identifies mathematical break points (discontinuities) to naturally avoid zero-convergence bounds.
* Derives active pointwise variables (Mean Squared Error, Maximum Pointwise Amplitude, and Absolute Convergence Proximity).
* Maps error ratios against dynamic user limits.

---

## 📐 Mathematical Architecture

The mathematical logic is explicitly programmed for absolute precision. Here are the true formulas utilized natively inside the Javascript engine bounds:

### 🟧 Square Wave
The Square Wave is fundamentally an "Odd" function over its domain. Because of its origin symmetry, the coefficient $a_n$ cancels symmetrically to exactly zero. The amplitude generation logic utilizes purely the $b_n$ limits:
```math
f(x) = \sum_{n=1,3,5...}^{\infty} \frac{4}{n\pi} \sin(nx)
```
* **Script Integration**: The Javascript strictly tests `(k % 2 === 0)` to intercept zero coefficients before rendering, drastically reducing loop bloat overhead by safely skipping even parameters internally.

### 🔺 Triangle Wave
Like the square formulation, testing enforces zero-limits for all even combinations of `n`. The active formula switches vector polarities utilizing a $4n$ loop pattern boundary:
```math
f(x) = \sum_{n=1,3,5...}^{\infty} \frac{8 (-1)^{\frac{n-1}{2}}}{n^2 \pi^2} \sin(nx)
```
* **Script Integration**: Handled explicitly via `const sign = (k % 4 === 1) ? 1 : -1;` to enforce perfect algebraic alignment.

### 🪚 Sawtooth Wave
The Sawtooth generation requires evaluation of every sequential harmonic parameter continuously rather than oscillating.
```math
f(x) = \sum_{n=1}^{\infty} \frac{2 (-1)^{n+1}}{n\pi} \sin(nx)
```

---

## 📂 Project Architecture

```bash
Fourier-viz-engine/
│
├── index.html       # Singular Compiled Execution File
│             - Core Architecture (HTML5 Canvas Engine)
│             - Style System (Custom Glassmorphism UI bounds)
│             - Execution System (FourierEngine, FourierRenderer)
│
└── README.md        # Mathematical documentation & limits
```

### Why a Single File?
The architecture specifically implements robust Single-Page Application (SPA) paradigms internally without invoking NPM, React, Angular, or external libraries. 
**Why?** Because computing complex infinite-limit algorithms concurrently over $50 \times 200$ dimensional spatial vectors per frame dictates extreme reduction of stack traces. Native Vanilla JS object instances ensure exact memory pointers without Virtual DOM bloat.

---

## 🛠 Technical Implementation

### The Core Engine Class
The mathematical derivation is governed entirely by `FourierEngine`, an encapsulated OOP script wrapper.

```javascript
// Excerpt of the analytical evaluation matrix bounds
evaluate(x, type, K, phaseOffset) {
    let sum = 0;
    let termsAdded = 0;
    let n = 1;
    
    // Explicit limit loop preventing memory leaks
    while (termsAdded < K) {
        const coeff = this.getCoefficients(type, n);
        
        // Zero-skipping algorithmic enhancement
        if (coeff.bn !== 0 || coeff.an !== 0) {
            const arg = n * x;
            sum += coeff.an * Math.cos(arg) + coeff.bn * Math.sin(arg);
            termsAdded++;
        }
        n++;
    }
    return sum;
}
```

### The Rendering Pipeline
The physical lines traced across the UI are passed instantly through `FourierRenderer.prototype.drawScale`. It converts pure logical coordinates mapping into localized DOM visual inputs directly on the viewport standardizations natively without loading ChartJS dependencies.

---

## 🚀 Execution & Usage

Because of its zero-dependency physical stack, the application execution requires zero installation, node modules, or compile systems. 

**Running the Application:**
1. Clone this repository directly.
   `git clone https://github.com/sathishr-ai/Fourier-viz-engine.git`
2. Open `index.html` inside any absolute modern web browser (Edge, Chrome, Webkit).
3. The engine engages instantly.

**Interacting with the Engine:**
* Select the targeted mathematical geometry via the dropdown menu bounds.
* Scale the `Number of Harmonics` parameter bounds upward to mathematically trigger additive sum combinations recursively.
* Launch the `Play Animation` interface to watch the exact linear chronological derivation bound frame-by-frame across limits.

---

## 📈 Analyzing The Output (Error Metrics)

During operation, observe the **Analysis** metric boxes on the UI console limit interface.
* **Convergence Progress**: Derived by establishing the current iteration Mean Squared Error as an absolute scale mapped against the index=1 MSE vector parameter natively.
* **Gibbs Phenomenon Overshoot**: You will visibly note that regardless of extending the limit parameters maximally to $N=50$, discrete discontinuous limits (`x = ±π` on Square algorithms) will retain a distinct $~9\%$ approximation anomaly boundary! This mathematically proves the geometric limits of infinite trigonometric series summation correctly.

---

## 📋 License & Modification

Designed strictly for Academic Portfolio utilization. The logic loops are heavily optimized, but further algorithmic derivations (Exponential bounds, Phase offsets, customized waveform limit matrices) can be freely injected directly into the `getCoefficients` block arrays!

<div align="center">
  <br />
  <strong>Developed purely via Vanilla Javascript & Native Math libraries</strong>
</div>
