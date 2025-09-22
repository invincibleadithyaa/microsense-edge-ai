# MicroSense-Edge-AI  

Microwatt Momentum 2025 Hackathon Project  
**Extending the Microwatt CPU with a Sensor Interface and Tiny AI Accelerator for Edge Applications**

---

## 🔹 Project Summary
Microwatt (open POWER CPU core) will be extended with:
1. **Sensor Interface** — allows Microwatt to read sensor data (simulated or via a simple bus).
2. **Tiny AI Accelerator** — a small MAC (multiply-accumulate) block that performs lightweight neural network operations.

This demonstrates **Microwatt for IoT + AI edge computing** — a CPU that can sense and think.

---

## 🔹 Why This Matters
IoT devices often read sensors but struggle with AI workloads. By adding an accelerator, Microwatt becomes capable of real-time processing at the edge.  
This is a step toward **open, customizable CPUs for smart edge applications**.

---

## 🔹 Deliverables
- Verilog RTL for sensor interface & accelerator  
- Testbenches and integration with Microwatt  
- Block diagram and documentation  
- Simulation results & demo video  

---

# Proposal: MicroSense-Edge-AI  

**Microwatt with Sensor Interface and Tiny AI Accelerator for Edge Applications**  
Microwatt Momentum Hackathon 2025

---

## Summary
This project extends the open-source Microwatt POWER CPU core with two new Verilog modules:

1. **Sensor Interface** – enables Microwatt to read sensor data (simulated values, or connected via a simple bus like I²C/SPI).  
2. **Tiny AI Accelerator** – a small multiply–accumulate (MAC) block that performs the core operation used in neural networks.

With these two modules, Microwatt will be able to fetch sensor values, pass them to the accelerator, and receive processed results. The end goal is to demonstrate **Microwatt as a practical IoT + Edge AI platform**.

---

## Motivation
IoT devices are everywhere, from wearables to smart sensors. They often rely on lightweight CPUs that can read data but struggle with AI workloads. At the same time, edge AI is becoming critical for low-latency and private inference.

By adding both a **sensor input path** and a **tiny AI accelerator** to Microwatt, we show how open-source CPUs can evolve into **custom, smart edge systems**. This will also serve as a reproducible learning project for the open hardware community.

---

## Architecture
- **Microwatt CPU Core** (baseline open POWER core).  
- **Sensor Interface (`sensor_if.v`)**:  
  - Memory-mapped registers accessible to Microwatt.  
  - Provides a stream/vector of sensor data.  
  - Starts as a simulated sensor; can later be extended to real I²C/SPI.  
- **AI Accelerator (`accelerator.v`)**:  
  - Simple MAC unit (multiply–accumulate).  
  - Takes input and weights, computes dot products.  
  - Controlled by registers (`start`, `done`, `result`).  
- **Integration (`top.v`)**:  
  - Instantiates Microwatt + peripherals.  
  - Microwatt program flow: Read Sensor → Send Data to Accelerator → Get Result.

---

## Expected Flow
1. Sensor interface produces a sample vector (e.g., [10, 20, 30]).  
2. Microwatt reads the data into memory.  
3. Microwatt writes it to the accelerator.  
4. Accelerator computes weighted sum (e.g., 10×1 + 20×2 + 30×3 = 140).  
5. Microwatt reads the result and prints/logs it.  

This shows a **full sensor-to-inference loop** on an open CPU.

---

## Deliverables
- Verilog RTL for sensor interface and accelerator.  
- Integration wrapper and testbenches.  
- Documentation: block diagram, register map, run instructions.  
- Example simulation output (waveforms, logs).  
- Final short demo video.  
- Open-source release under MIT license.

---

## Tools & Technologies
- Microwatt CPU core (OpenPOWER Foundation)  
- Verilog/SystemVerilog for modules  
- Yosys, Verilator, NextPNR (simulation/synthesis)  
- GitHub for repo & reproducibility  
- (Optional) OpenLane / SKY130 precheck flow for ASIC

---

## Timeline
- **Week 0 (Proposal):** Repo with README, proposal, block diagram, skeleton files.  
- **Week 1–2:** Sensor interface development + testing with Microwatt.  
- **Week 2–3:** Tiny AI accelerator (MAC unit), standalone testbenches.  
- **Week 3–4:** Integration: Microwatt ↔ Sensor_IF ↔ Accelerator.  
- **Week 4–5:** Verification, waveforms, docs.  
- **Week 6:** Demo video + repo polish + final submission.

---

## Team
- **Adithya A** (GitHub: [invincibleadithyaa](https://github.com/invincibleadithyaa))  
- **Arjun Saiju** (GitHub: [ArjunSaiju](https://github.com/ArjunSaiju))  
- **Asil Fawaz** (GitHub: [Asil-projects](https://github.com/Asil-projects))  
- **Anush P** (GitHub: [Anush-Kashyap](https://github.com/Anush-Kashyap))
- **Johan Shibu** (GitHub: [johanshibu3-alt](https://github.com/johanshibu3-alt)) 

---

## License
All code and docs will be released under the MIT License to ensure open collaboration and reproducibility.


