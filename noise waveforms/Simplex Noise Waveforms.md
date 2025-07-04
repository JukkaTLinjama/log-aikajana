# Repeating Morphing Noise Waveform with Log FFT and DC Readout

This project is a single-page interactive HTML application that visualizes a looping noise waveform and its frequency spectrum. The waveform is generated with 2D Simplex noise and forced to fade to zero at both ends to ensure seamless loops.

## Features

✅ **Time-Domain Waveform**

* Drawn in the top canvas (`waveformCanvas`).
* Uses a cosine fade-in/out window (32 samples on each end) to smoothly force the waveform to zero.
* Prevents clicks or pops in audio looping.

✅ **Frequency-Domain (FFT) Plot**

* Plots the magnitude of the FFT of the waveform.
* Y-axis shows magnitude in decibels (0 dB at top, -100 dB at bottom).
* X-axis shows frequency bins on a logarithmic scale, giving more detail in lower frequencies.
* Tick marks and labels for both dB and frequency bins.

✅ **DC Component Readout**

* Numerically displays the DC (k=0) magnitude in dB above the FFT plot.
* Helps assess residual DC offsets even if the window forces the waveform towards zero.

✅ **Interactive Sliders**

* **Vertical Line (0-256)**: Moves the vertical line across the noise plane, morphing the waveform.
* **Base Frequency**: Controls the base frequency of the noise sampling.
* **Octaves**: Adds fractal noise layers for more complexity.

## Technologies

* **JavaScript**: Core simulation and rendering logic.
* **HTML5 Canvas**: Waveform and FFT visualization.
* **SimplexNoise**: Custom 2D Simplex noise implementation with deterministic seeding (Mulberry32 PRNG).
* **Manual DFT**: Computes the FFT using direct calculation of the Discrete Fourier Transform (DFT) without libraries, ensuring transparency in calculations.

## Details of Implementation

* **Waveform Generation**

  * 256 samples per frame.
  * Noise is evaluated at `xNorm * freq, yOffset/32`.
  * Octave summing creates fractal noise; amplitude halves with each octave.
  * The result is normalized by the sum of amplitudes to keep output near \[-1,1].

* **Windowing**

  * Uses a raised cosine (Hann-like) window on first and last 32 samples.
  * Ensures waveform fades to zero smoothly.

* **FFT Calculation**

  * Calculates real and imaginary parts directly for each frequency bin.
  * Computes magnitude from sqrt(re² + im²) for each bin.
  * Converts to decibels relative to the maximum magnitude.

* **Logarithmic Frequency Axis**

  * X-axis is mapped as `log10(bin index)` scaled across canvas width.
  * Frequency tick marks at bins: 1, 2, 5, 10, 20, 50, 100.

* **DC Component**

  * k=0 bin is not plotted on log scale but read and displayed numerically.

* **Rendering**

  * Uses two canvases: one for the waveform, one for the FFT.
  * Gridlines and labels are added for readability.
  * Sliders trigger redraws on input.

## Usage

1. Open the HTML file in a modern web browser (Chrome, Firefox, Edge).
2. Use sliders to morph the waveform and observe how the time-domain and frequency-domain plots change.
3. Watch the DC readout in the FFT plot to monitor waveform bias.

## Customization

* Adjust `samples`, `fadeSamples`, or noise seed in the script for different resolutions or randomness.
* Extend frequency labels or add Hz scaling based on your application needs.

## License

This project is provided for educational and experimental use. Feel free to modify it for your projects.

---

Enjoy exploring morphing waveforms and their spectral properties!
