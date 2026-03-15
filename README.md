# Laplace Transform Pole-Zero Explorer

Interactive pole-zero editor for exploring Laplace-domain transfer functions — drag poles and zeros, watch impulse response and Bode plots respond in real time.

### [Launch App](https://brendanjameslynskey.github.io/Laplace_Pole_Zero_Explorer/)

---

## What is this?

A single-page web app that lets you build transfer functions visually on the complex s-plane and immediately see how pole and zero placement affects time-domain behaviour (impulse response) and frequency-domain characteristics (Bode magnitude and phase). Ideal for students and engineers studying control systems, signal processing, or circuit theory.

## Presets

| Preset | Poles | Zeros | Description |
|--------|-------|-------|-------------|
| First-order LP | 1 real | — | Simple RC-type lowpass |
| 2nd-order Underdamped | Complex pair | — | Oscillatory step response |
| 2nd-order Overdamped | 2 real | — | Sluggish, no overshoot |
| Notch Filter | Complex pair | Imaginary pair | Rejects a single frequency |
| Lead Compensator | 1 real (far) | 1 real (near) | Adds phase lead for stability |
| Lag Compensator | 1 real (near) | 1 real (far) | Boosts low-frequency gain |
| PID Controller | Origin | 2 real | Proportional-integral-derivative |
| Resonant Circuit | Complex pair | Origin | Bandpass-like response |
| Butterworth 2nd | 45-degree pair | — | Maximally flat magnitude |
| All-pass Filter | 1 real (LHP) | 1 real (RHP) | Unity gain, phase shift only |

## Features

- **S-plane editor** — click to place poles or zeros; complex entries auto-generate conjugate pairs
- **Impulse response** — computed via partial-fraction expansion and inverse Laplace transform
- **Bode plots** — magnitude (dB) and phase (degrees) on a shared frequency axis
- **Stability indicator** — real-time STABLE / UNSTABLE badge based on pole locations
- **Transfer function display** — expanded polynomial form of H(s)
- **10 built-in presets** — one-click loading of classic systems
- **Fully interactive** — Plotly.js pan, zoom, and hover on every plot
- **Responsive** — works on desktop and mobile

## Built with

- [Plotly.js](https://plotly.com/javascript/) for interactive plotting
- Vanilla HTML/CSS/JS — no build step, no dependencies to install
