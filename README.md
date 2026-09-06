# Fourier Series Convergence Visualizer 📈

An interactive mathematical engine built entirely in Vanilla JavaScript to demonstrate the convergence of Fourier Series and the Gibbs Phenomenon natively at 60fps.

## Features
* **Real-time Analytical Integration**: Calculates true $a_n$ and $b_n$ values over 200 physical data points rather than using numerical approximations.
* **Dynamic Convergence**: Watch in real-time as complex shapes (Square, Triangle, Sawtooth) converge mathematically up to $N=50$ iterations.
* **Additive Synthesizer Breakdown**: Explodes the final geometry into individual harmonic cosine and sine waves via the dynamic scaling UI.
* **Error Analysis**: Calculates the exact pointwise Mean Squared Error ignoring extreme boundaries specifically for visualizing decay independent of jump discontinuities. 

## Technology Stack
* Pure HTML5
* CSS3 (Glassmorphism & Flexbox mapping)
* Vanilla ES6 JavaScript (zero external dependencies)
* Native Canvas API Rendering

## Usage
Simply open `index.html` in any modern web browser to run the application immediately. No server or backend configuration required.
