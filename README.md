# 🌊 Charvak Dam Break Simulation

<p align="center">
  <strong>🌐 Read in:</strong>
  <a href="README.md"><strong>English</strong></a> |
  <a href="README.uz.md"><strong>O'zbekcha</strong></a> |
  <a href="README.ru.md"><strong>Русский</strong></a>
</p>

[![Live Simulation](https://img.shields.io/badge/Live_Demo-Interactive_3D_Simulation-00d084?style=for-the-badge&logo=githubpages&logoColor=white)](https://charvak-simulation.github.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Physics: SERGHEI + LISFLOOD](https://img.shields.io/badge/Solvers-SERGHEI%202D%20SWE%20%26%20LISFLOOD--FP-orange?style=for-the-badge)](https://charvak-simulation.github.io/)

> 🌐 **Interactive 3D WebGL Simulation:**  
> 👉 **[https://charvak-simulation.github.io/](https://charvak-simulation.github.io/)**  
> 📊 **Full Technical & Hydrological Reference Data:**  
> 👉 **[CHARVAK_DATA.md](CHARVAK_DATA.md)**

---

## What happens if the Charvak Dam breaches?
This open scientific project provides high-resolution 2D hydrodynamic modeling of a hypothetical catastrophic dam break at the **Charvak Reservoir** (Bostanlyk district, Tashkent region, Uzbekistan) along the Chirchik River basin using **2D Shallow Water Equations (SWE)**.

The simulation was developed with computation carried out on GPU (NVIDIA CUDA) accelerators across tens of solver hours to model the flood wave from the dam crest down to the Shardara Reservoir in Kazakhstan.

---

## 🔬 Technical Specification & Numerical Methods
* **Reservoir Volume:** 2.0 km³ (2.0 billion m³).
* **Dam Structure:** Rockfill dam with central earthen core, height 168 m, crest elevation 900 m a.s.l.
* **Breach Hydrograph Formulation:** Froehlich (2008) embankment dam failure model.
* **Peak Outflow Discharge (Qp):** approximately 182,013 m³/s.
* **Breach Formation Time (tf):** 1.6 hours.
* **Numerical Engines:**
  * **SERGHEI** (GPU-accelerated, Roe Riemann upwind finite-volume SWE solver) on a 60 m grid with 5-minute output frames.
  * **LISFLOOD-FP 8.1** (Local-inertial formulation) on a 90 m grid with 15-minute output frames.
* **Elevation Datasets (DEM):** Copernicus DEM GLO-30 (DSM), Bristol/Fathom FABDEM v1.2 (bare-earth), JAXA ALOS World 3D (AW3D30), NASADEM, NASA SRTM GL1.

---

## ⏱️ Flood Wave Travel Times & Impact Matrix

| Elapsed Time | Location | Hydrodynamic Impact & Inundation Depth |
| :--- | :--- | :--- |
| **0 – 15 min** | **Bochka Gorge** (Immediate downstream) | Initial surge wave peak. Depths exceed 60–100+ m. Khojikent dam is overwhelmed. |
| **1 hour** | **Gazalkent** | Wave front arrives. Maximum inundation depth: 17–23 m. |
| **2 hours** | **Chirchik City** | Main industrial hub flooded. Flow depth: 16–21 m. Severe hazard to chemical production plants. |
| **2.5 – 3 hours** | **Qibray & Yangibozor** | Flood leaves narrow mountain canyon into piedmont alluvial fan. Yangibozor is extensively submerged. |
| **3.5 – 4 hours** | **Tashkent Ingress (Kuyluk / Qo'yliq)** | Flood enters southeastern capital limits. Inundation of the Chirchik river floodplain and Kuyluk market perimeter. |
| **4.5 – 5 hours** | **Sergeli & Mirobod Lowlands** | Substantial inundation across Sergeli, the "Index" logistics park, and low-lying parts of Mirobod. |
| **6 – 7 hours** | **Airport Zones & Mirzo Ulugbek** | Both local and international airports suffer runway and terminal flooding. Fluvial backwater affects low-lying areas. |
| **9 – 10 hours** | **Small Ring Road & South Railway** | Flow expands up to the Small Ring Road boundary. Yakkasaroy district partially inundated; threat to South Railway Station. |
| **10.5 – 13 hours**| **Sergeli Elevated Metro & Zangiota** | Flood reaches elevated metro line pylons and spreads through agricultural lowlands of Zangiota. |
| **24 hours** | **Shardara Reservoir (Kazakhstan)** | Flood wave passes Chinaz into the Syr Darya and enters Shardara. If Shardara is at capacity (5–7 km³), risk of catastrophic cascading failure. |

---

## 🧠 Debunking the Urban Legend (Why Central Tashkent Stays Dry)
Popular urban myths frequently claim that a Charvak dam failure would submerge the entirety of Tashkent within 10–20 minutes. The physics-based simulation refutes this:
1. **Wave Velocity Constraints:** Over the 60 km river distance, the wave propagation velocity is 12–18 km/h (3.5–5 m/s), meaning the flood front takes **3.5 to 4 hours** to reach the borders of Tashkent.
2. **Terrace Geomorphology:** Tashkent is built on a succession of elevated Quaternary fluvial terraces. Yunusabad, Shaykhontohur, Mirzo Ulugbek highlands, and the city center (Amir Timur Square) are situated **20 to 50+ meters above the Chirchik riverbed**.
3. **Hydrodynamic Result:** The computational gauge probe at central Tashkent registers **0.00 m flood depth**. Inundation is physically confined to the southern Chirchik floodplain and lowlands.

---

## ❓ Frequently Asked Questions (FAQ)

### Will Tashkent be submerged if the Charvak Dam breaches?
**No.** Central and northern Tashkent (Amir Timur Square, Yunusabad, Shaykhantahur, Mirzo Ulugbek highlands) remain completely dry because they sit on elevated Pleistocene river terraces **20 to 50+ meters above the Chirchik riverbed**. Hydrodynamic modeling demonstrates **0.00 m flood depth** at central Tashkent. Flooding is strictly confined to the Chirchik river floodplain and southern lowlands (Bektemir, Qo'yliq, Sergeli, and southern Zangiata).

### How long does the flood wave take to reach Tashkent?
**3.5 to 4 hours.** The distance along the Chirchik riverbed is over 60 km, and the wave front travels at 12–18 km/h (3.5–5 m/s). Claims that Tashkent would be submerged in 10–20 minutes are physically impossible.

### What is the flood wave arrival timeline for settlements?
* **Bochka Gorge:** 0–15 min (60–100+ m depth)
* **Gazalkent:** 1 hour (17–23 m)
* **Chirchik City:** 2 hours (16–21 m)
* **Yangibozor:** 2.5–3 hours
* **Tashkent limits (Kuyluk):** 3.5–4 hours
* **Sergeli:** 4.5–5 hours
* **Chinaz:** 18 hours
* **Shardara Reservoir (Kazakhstan):** 24 hours

### What numerical models and breach parameters were used?
2D Shallow Water Equations solved via **SERGHEI** (60 m grid, GPU Roe Riemann solver) and **LISFLOOD-FP 8.1** (90 m grid). Embankment dam breach modeled via **Froehlich (2008)**: peak outflow discharge Qp ≈ 182,013 m³/s, breach formation time tf = 1.6 hours, reservoir storage 2.0 km³, dam height 168 m. Elevation data: Copernicus DEM GLO-30 and FABDEM.

---

## 📜 License & Citation
The code and web visualizer are released under the [MIT License](LICENSE).  
Topographic datasets: Copernicus DEM GLO-30 (© ESA/Airbus), FABDEM (© University of Bristol / Fathom), ALOS World 3D (© JAXA).
