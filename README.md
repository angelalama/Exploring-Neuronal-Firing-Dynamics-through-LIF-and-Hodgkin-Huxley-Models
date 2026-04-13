# Exploring-Neuronal-Firing-Dynamics-through-LIF-and-Hodgkin-Huxley-Models

## Overview
In this project I explore neuronal firing dynamics through the implementation and comparison of two fundamental computational models: the **Leaky Integrate-and-Fire (LIF)** model and the **Hodgkin-Huxley (HH)** model. 
The goal is to analyze how neurons generate spikes, how firing rates depend on input current, and how different model assumptions affect neuronal behavior.Also, I focus on deeply understand these models from the neurocomputational aspect. This project represents my first independent exploration in computational neuroscience.

## Models Implemented

### Leaky Integrate-and-Fire (LIF)
The LIF model is a simplified representation of neuronal activity. In this model, membrane potential evolves according to a linear differential equation. Also, spikes are generated when a threshold is reached. It is characterized by:
* Fixed firing threshold (in this case, I am using a value of V_thresh = -55)
* Reset mechanism after spike (in this case, V_reset = -75)
* Refractory period (in this case is 10 ms, and is the time after a spike when a neuron can not fire another spike)
* Controlled by parameters such as membrane resistance (R=1.5), time constant (τau_m=10), and threshold (V_thresh=-55)

### Hodgkin-Huxley (HH)
The Hodgkin-Huxley model is a biophysical model that describes neuronal dynamics through voltage-gated ion channels. Compared to the LIF model, the HH model is more complex and biologically grounded. It is characterized by:
* Sodium (Na⁺), potassium (K⁺), and leak currents
* Gating variables (m, h, n) controlling ion channel dynamics
* Realistic spike generation based on ionic mechanisms
* Conductance parameters (gNa=120, gK=36, gL=0.3) determine excitability

## Results

### Membrane Potential Dynamics (LIF)
- Fig2.png
The LIF model exhibits abrupt spike generation once the membrane potential crosses a fixed threshold. This results in regular and sharp firing patterns. The figure generated doesn't model ion channels because the spike is “artificial.” This means that it only reaches the threshold and then resets. Therefore, in the graph, it never goes much beyond 0 mV (or even cuts off before that).

### Membrane Potential Dynamics (HH)
- Fig1.png
The Hodgkin-Huxley model produces smooth and biologically realistic action potentials driven by the interaction of ion channels. The figure models Na⁺ and K⁺ channels, and when activated, Na⁺ flows in massively. As a consequence, the result is that the voltage rises to +30 / +40 mV, and that is why the peaks are much higher than in the LIF model.

### Model Comparison
- Fig3.png
While both models generate spikes, the LIF model produces idealized threshold-based firing, whereas the HH model captures detailed spike shapes and dynamics. 
There is a difference in the downward phase. On the one hand, in LIF, the voltage drops instantly due to the equation used (V = V_reset). This creates an artificial vertical drop. On the other hand, in HH, the voltage drops gradually because Na⁺ channels close and K⁺ channels open, resulting in a realistic repolarization.

### Spike Timing Comparison
- Fig3.png
In spike timing, we observe that spikes are more frequent in HH because it has active dynamics, whereas in LIF, spikes are slightly more spaced out because it is limited by the refractory period.

### F-I Curves (Firing Rate vs Input Current)
- Fig4.png
The LIF model exhibits an abrupt onset of firing due to its fixed threshold and linear dynamics, resulting in a sharp transition from silence to repetitive spiking. In contrast, the Hodgkin-Huxley model shows a gradual increase in firing rate, as spike generation emerges from the nonlinear interaction of voltage-gated ion channels, leading to a smooth and ly realistic response.

### Parameter Effects (LIF)
- Fig5.png
* At a lower threshold: the curve shifts to the left because, as V_thresh decreases, less current is needed to reach the spike, making it easier to trigger. 
* In Higher R: it also shifts to the left (but in a different way) because in V=RI, if R increases, the voltage rises more with the same current. Thus, the threshold is reached faster, and firing can occur with a lower I.
The difference between these two is that in threshold, the firing condition changes, while in R, how the voltage builds up changes

### Parameter Effects (HH)
- Fig6.png
* At higher gNa: the curve shifts upward and to the left. This occurs because Na⁺ depolarizes (increases the voltage), and if gNa is increased, more Na⁺ enters and the spike is triggered more easily. As a result, the firing rate increases and the spike begins earlier.
* In  Higher gK: the curve shifts to the right and down. This is because K+
repolarizes (lowers the voltage), and if gK is increased, the neuron “turns off” faster and is harder to trigger. Therefore, more current is needed and the frequency is lower.
* At Baseline: This is the natural balance between: Na⁺ (excites) and K⁺ (inhibits)

### All Parameter Effects (LIF and HH)
- Fig7.png
In the LIF model, parameter changes such as threshold and membrane resistance primarily shift the F-I curve by altering the effective input required to reach firing. In contrast, in the Hodgkin-Huxley model, changes in ion channel conductances (gNa, gK) modify the intrinsic excitability and nonlinear dynamics of the system, which leads to more complex transformations in both the slope and shape of the F-I relationship.

## Key Insights
* The **LIF model** captures essential spike timing using a simple threshold mechanism.
* The **Hodgkin-Huxley model** utilizes a more detailed and ly description of neuronal activity. It is more realistic.
* Parameter variations affect excitability differently in each model.
* The HH model shows smoother F-I curves, while LIF exhibits sharp transitions.

## Methods
The simulations were performed using Python with:
* NumPy for numerical computation
* Matplotlib for visualization

For spike detection:
* LIF: threshold crossing
* HH: zero-crossing (V < 0 → V ≥ 0)

## Conclusion
The LIF model has a simple, nearly linear F-I relationship, with an abrupt onset of firing due to its fixed threshold and passive dynamics. Also, changes in the threshold or membrane resistance cause shifts in the curve, as they alter the current required to generate activity without significantly altering the shape of the response.
In contrast, the Hodgkin-Huxley (HH) model exhibits a nonlinear and gradual F-I relationship. This is due to the dynamic interaction between voltage-gated ion channels. Furthermore, variations in sodium (gNa) and potassium (gK) conductances not only shift the curve but also alter its shape. Therefore, an increase in gNa increases excitability and firing rate, while an increase in gK has the opposite effect.
In conclusion, while the LIF model provides a simplified representation of general neuronal firing behavior, the HH model offers a more realistic and biologically grounded description, capable of reproducing complex dynamics of excitability.

## Future Work
* Extend to network simulations
* Incorporate noise and stochastic inputs
* Explore learning rules and plasticity
* Apply machine learning to neural data
