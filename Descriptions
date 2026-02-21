# Synthetic dataset (description)

- Source: high-fidelity synthetic IoT-Serious-Game (IoTeSG) generator included in this repo. 
- Records: 4,500 multi-modal records produced by simulating 500 time steps × 3 player profiles × 5 sensor nodes.
- Modalities included:
  - Environmental: temperature, humidity, ambient audio level, chemical concentration spikes. Temperature: diurnal sinusoid (mean 22°C, amplitude 2°C). Noise (generator) σ ∈ [0.5, 1.5] for environmental channels.
  - Physiological: heart-rate (clipped to 40–180 bpm), EEG alpha (5–20 μV). Motion: 3-axis accelerometer & gyroscope.
  - Gameplay: GameScore, GameDifficulty, PlayerEngagement (normalized to [0,1]).
- Preprocessing applied by scripts:
  - clipping to physiologically/physically plausible ranges (e.g., HR 40–180 bpm; EEG alpha 5–20 μV; temperature 15–35°C), unit normalization (and optional standardization). Generator-level Gaussian noise std in experiments varied ≈ 0.5–3.0 depending on channel. 
- Sensor uptime / dropouts:
  - Uptime simulated ≈ 85% with Bernoulli trials; occasional dropouts inserted to simulate connectivity variability.
- Known limitations:
  - Dataset is synthetic and reflects modeled noise/regimes. Real-world sensor drift, >5% packet loss, or non-Gaussian corruption can reduce empirical performance vs. the simulated results (see manuscript Section on limitations).
