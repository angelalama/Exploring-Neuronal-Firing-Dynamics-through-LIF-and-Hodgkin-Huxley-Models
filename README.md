# Exploring-Neuronal-Firing-Dynamics-through-LIF-and-Hodgkin-Huxley-Models

## Overview

In this project I explore neuronal firing dynamics through the implementation and comparison of two fundamental computational models: the **Leaky Integrate-and-Fire (LIF)** model and the **Hodgkin-Huxley (HH)** model.

The goal is to analyze how neurons generate spikes, how firing rates depend on input current, and how different model assumptions affect neuronal behavior.Also, I focus on deeply understand these models from the neurocomputational aspect.


## Models Implemented

### Leaky Integrate-and-Fire (LIF)

The LIF model is a simplified representation of neuronal activity, where membrane potential evolves according to a linear differential equation and spikes are generated when a threshold is reached.

Key characteristics:

* Fixed firing threshold
* Reset mechanism after spike
* Refractory period
* Controlled by parameters such as membrane resistance (R), time constant (τ), and threshold

---

### Hodgkin-Huxley (HH)

The Hodgkin-Huxley model is a biophysical model that describes neuronal dynamics through voltage-gated ion channels.

Key characteristics:

* Sodium (Na⁺), potassium (K⁺), and leak currents
* Gating variables (m, h, n) controlling ion channel dynamics
* Realistic spike generation based on ionic mechanisms
* Conductance parameters (gNa, gK, gL) determine excitability

---

## 📊 Results

### Membrane Potential Dynamics (LIF)

![LIF](figures/lif_voltage.png)

The LIF model exhibits abrupt spike generation once the membrane potential crosses a fixed threshold. This results in regular and sharp firing patterns.

---

### Membrane Potential Dynamics (HH)

![HH](figures/hh_voltage.png)

The Hodgkin-Huxley model produces smooth and biologically realistic action potentials driven by the interaction of ion channels.

---

### Model Comparison

![Comparison](figures/comparison.png)

While both models generate spikes, the LIF model produces idealized threshold-based firing, whereas the HH model captures detailed spike shapes and dynamics.

---

### Spike Timing Comparison

![Spikes](figures/spike_comparison.png)

Spike timing differs slightly between models due to the underlying mechanisms of spike generation.

---

### F-I Curves (Firing Rate vs Input Current)

![FI](figures/fi_curve.png)

The LIF model shows an abrupt increase in firing rate after a threshold input current, whereas the HH model exhibits a more gradual and biologically realistic response.

---

### Parameter Effects (LIF)

![LIF Params](figures/lif_parameters.png)

Changing parameters such as threshold or membrane resistance shifts neuronal excitability and firing behavior.

---

### Parameter Effects (HH)

![HH Params](figures/hh_parameters.png)

Modifying ion channel conductances (gNa, gK) alters firing dynamics, reflecting the biological role of ion channels in neuronal activity.

---

## Key Insights

* The **LIF model** captures essential spike timing using a simple threshold mechanism.
* The **Hodgkin-Huxley model** provides a more detailed and biologically realistic description of neuronal activity.
* Parameter variations affect excitability differently in each model.
* The HH model shows smoother F-I curves, while LIF exhibits sharp transitions.

---

## Methods

Simulations were performed using Python with:

* NumPy for numerical computation
* Matplotlib for visualization

Spike detection:

* LIF: threshold crossing
* HH: zero-crossing (V < 0 → V ≥ 0)

---

## Project Structure

```
Exploring-Neuronal-Firing-Dynamics/
│
├── notebook.ipynb
├── lif_model.py
├── hodgkin_huxley.py
│
├── figures/
│   ├── ...
│
└── README.md
```

---

## Conclusion

This project highlights the trade-off between simplicity and biological realism in neuronal modeling. While simplified models such as LIF are useful for large-scale simulations, detailed models like Hodgkin-Huxley are essential for understanding the underlying mechanisms of neural activity.

---

## Future Work

* Extend to network simulations
* Incorporate noise and stochastic inputs
* Explore learning rules and plasticity
* Apply machine learning to neural data

---
