# D2D Resource Allocation and Analysis

## Overview  
This repository contains the implementation of **Bipartite Graph-Based Proportional Fair Resource Allocation for D2D Communication** based on the paper:  

**[1]** “Bipartite Graph Based Proportional Fair Resource Allocation for D2D Communication.”  

The project focuses on simulating **Device-to-Device (D2D) communication** within a **single hexagonal cell**, modeling **resource allocation, path loss, and fast fading effects**. The simulation assumes **perfect channel state information (CSI)** at the receiver, ensuring accurate estimation of channel gains:  

- **gₖcB[n]** → Channel gain between Cellular User (CU) and Base Station (B)  
- **gₖcdR[n]** → Channel gain between CU and D2D Receiver (dR)  
- **gₖdTdR[n]** → Channel gain between D2D Transmitter (dT) and D2D Receiver (dR)  
- **gₖdTB[n]** → Channel gain between D2D Transmitter (dT) and Base Station (B)  

---

## Simulation Procedure  
The simulation consists of **three major phases**:

1. **Resource Block (RB) Allocation to Cellular Users (CUs)**  
   - Assign RBs to CUs while maintaining fairness.  

2. **SNR Calculation and Power Allocation for D2D Users**  
   - Compute **SNR for each CU** and analyze **interference levels**.  
   - Determine optimal **power and rate allocation** for D2D users sharing the same RBs.  

3. **Optimal RB Selection for D2D Users**  
   - Calculate **achievable data rates** and select the best **RB-D2D pairs**.  

---

## Simulation Parameters  
The following parameters were used to simulate **5000 devices** in Python:

| **Parameter**                    | **Value**      |
|----------------------------------|--------------|
| **Cell layout**                   | Single hexagonal cell |
| **Radius**                         | 500m |
| **Spectrum allocation (uplink)**    | 5 MHz |
| **Resource block bandwidth**        | 180 kHz |
| **Available resource blocks**       | 25 |
| **Max D2D transmit power**          | 250 mW |
| **Max CU transmit power**           | 250 mW |
| **User distribution**               | Uniform |
| **Number of CUs (NC)**              | 20 |
| **Number of D2D pairs (ND)**        | 2 - 22 |
| **Path loss model**                 | 128.1 + 37.6log(d) |
| **Fast fading**                     | Rayleigh Fading |
| **UE noise figure**                 | 5 dB |
| **UE thermal noise density**        | -174 dBm/Hz |

---

## Data Generation & ETL Process  
A **Python script** was developed to **generate realistic data** for 5000 devices based on the above parameters. The data includes:  

✔ **Distance** between devices  
✔ **Path loss** calculations  
✔ **Received power (dBm)**  
✔ **Signal-to-Noise Ratio (SNR) (dB)**  
✔ **Data rate (Mbps) based on Shannon Capacity formula**  
✔ **Latency, Bandwidth, and other network metrics**  

The generated data underwent **ETL (Extract, Transform, Load) processes** to clean, structure, and format the dataset for analysis in **Power BI**.

---

## Power BI Dashboard Creation 🎨📊  
The dashboard provides a **comprehensive visualization** of the **D2D communication system performance**. It includes:  

📌 **Path Loss ,bandwidth,datarate & SNR Analysis:**  
- Scatter plots  comparing **interference vs datarate and bandwidth**,**Impact on datarate as distance between devices increase etc.**



The dashboard allows users to **filter and analyze the impact of distance, interference, and latency on datarate** on overall network performance.

