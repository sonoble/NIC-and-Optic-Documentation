# NVIDIA Network Interface Cards Reference Guide

## Overview

This document provides comprehensive information about NVIDIA's ConnectX SmartNIC/SuperNIC family and BlueField Data Processing Unit (DPU) series, including technical specifications, form factors, signaling technologies, and compatible optics/DAC cables.

## Document Version
- **Last Updated:** 2025-11-06
- **Scope:** ConnectX-6 through ConnectX-9, BlueField-3 and BlueField-4

---

## Table of Contents

1. [ConnectX Series Overview](#connectx-series-overview)
2. [ConnectX-6 Family](#connectx-6-family)
3. [ConnectX-7 Family](#connectx-7-family)
4. [ConnectX-8 SuperNIC](#connectx-8-supernic)
5. [ConnectX-9 SuperNIC](#connectx-9-supernic)
6. [BlueField-3 DPU](#bluefield-3-dpu)
7. [BlueField-4 DPU](#bluefield-4-dpu)
8. [Form Factors and Connectors](#form-factors-and-connectors)
9. [Signaling Technologies](#signaling-technologies)
10. [NVIDIA LinkX Optics and DACs](#nvidia-linkx-optics-and-dacs)
11. [Third-Party Compatible Optics](#third-party-compatible-optics)
12. [Compatibility Matrix](#compatibility-matrix)

---

## ConnectX Series Overview

The NVIDIA ConnectX family provides high-performance network connectivity for data centers, AI infrastructure, and HPC environments. The series supports both Ethernet and InfiniBand protocols (VPI - Virtual Protocol Interconnect models).

### Key Technologies

- **VPI (Virtual Protocol Interconnect):** Dual-mode support for both Ethernet and InfiniBand
- **RDMA:** Remote Direct Memory Access for low-latency, high-throughput networking
- **RoCE:** RDMA over Converged Ethernet
- **SR-IOV:** Single Root I/O Virtualization for efficient virtualization
- **GPUDirect:** Direct GPU-to-GPU communication

---

## ConnectX-6 Family

### Overview
The ConnectX-6 series provides 100/200Gb/s connectivity with support for both NRZ and PAM4 signaling.

### Models

#### ConnectX-6 Dx (Dual-Port)
- **Speeds:** 10/25/40/50/100Gb/s per port or single 200Gb/s
- **Form Factor:** QSFP56 or QSFP28
- **Host Interface:** PCIe 4.0 x16
- **SerDes Technology:** 50Gb/s PAM4 and 25/10Gb/s NRZ

#### ConnectX-6 Lx (Lower-Speed)
- **Speeds:** 10/25Gb/s
- **Form Factor:** SFP28
- **Host Interface:** PCIe 4.0 x8
- **SerDes Technology:** 25Gb/s NRZ

#### ConnectX-6 VPI (InfiniBand/Ethernet)
- **Speeds:** HDR InfiniBand (200Gb/s), EDR InfiniBand (100Gb/s), 100/200GbE
- **Form Factor:** QSFP56
- **Host Interface:** PCIe 4.0 x16

### Technical Specifications

| Feature | ConnectX-6 Dx | ConnectX-6 Lx | ConnectX-6 VPI |
|---------|---------------|---------------|----------------|
| Max Bandwidth | 200Gb/s | 50Gb/s | 200Gb/s |
| Ports | 2x 100Gb/s | 2x 25Gb/s | 2x 100Gb/s or 1x 200Gb/s |
| SerDes Lanes | 4 lanes per port | 1 lane per port | 4 lanes per port |
| Lane Speed | 50G PAM4 / 25G NRZ | 25G NRZ | 50G PAM4 / 25G NRZ |
| PCIe Gen | 4.0 x16 | 4.0 x8 | 4.0 x16 |
| Protocols | Ethernet | Ethernet | Ethernet, InfiniBand |

### Supported Cables and Optics

**Direct Attach Copper (DAC):**
- QSFP28 100G DAC: 1m, 3m, 5m lengths
- QSFP56 200G DAC: 1m, 2m, 3m lengths
- Breakout cables: 100G QSFP28 to 4x25G SFP28

**Active Optical Cables (AOC):**
- QSFP28 100G AOC: Up to 100m
- QSFP56 200G AOC: Up to 100m

**Optical Transceivers:**
- QSFP28 100G SR4 (multimode, 70-100m)
- QSFP28 100G LR4 (single-mode, 10km)
- QSFP56 200G SR4 (multimode, 70-100m)
- QSFP56 200G DR4 (single-mode, 500m)

### Example Part Numbers
- **MCX631102AN-ADAT:** ConnectX-6 Lx 2x25GbE, dual-port SFP28, PCIe 4.0 x8
- **MCX623106AC-CDAT:** ConnectX-6 Dx 2x100GbE, dual-port QSFP56, PCIe 4.0 x16

---

## ConnectX-7 Family

### Overview
The ConnectX-7 introduces 400Gb/s connectivity using 100G-PAM4 signaling, available in both QSFP112 and OSFP form factors.

### Models

#### ConnectX-7 QSFP112 Variants

**Single-Port 400GbE/NDR (QSFP112):**
- **Speeds:** 400Gb/s
- **Form Factor:** QSFP112
- **Host Interface:** PCIe 5.0 x16
- **SerDes Technology:** 100Gb/s PAM4 (4 lanes)
- **Part Number Example:** MCX75310AAS-NEAT

**Dual-Port 200GbE/NDR200 (QSFP112):**
- **Speeds:** 2x200Gb/s
- **Form Factor:** 2x QSFP112
- **Host Interface:** PCIe 5.0 x16
- **SerDes Technology:** 50Gb/s PAM4 per port (4 lanes each)
- **Part Number Example:** MCX75520AAS-NEAT

#### ConnectX-7 OSFP Variants

**Single-Port 400GbE/NDR (OSFP):**
- **Speeds:** 400Gb/s
- **Form Factor:** OSFP (Flat Top)
- **Host Interface:** PCIe 5.0 x16
- **SerDes Technology:** 100Gb/s PAM4 (4 lanes)
- **Part Number Examples:**
  - MCX75510AAS-NEAT (PCIe standard form factor)
  - MCX75343AAS-NEAC1 (OCP 3.0 TSFF)
  - MCX75343AMS-NEAC (OCP 3.0 TSFF, Multi-Host and Socket Direct)

**Key OSFP Features:**
- OSFP connectors support RHS (Riding Heatsink) cage only
- Available in PCIe Half Height, Half Length (HHHL) form factor
- Available in OCP 3.0 Tall Small Form Factor (TSFF)
- Socket Direct capable variants available
- Uses flat-top OSFP modules on NIC side (different from switch-side modules)

### Technical Specifications

| Feature | CX-7 Single QSFP112 | CX-7 Dual QSFP112 | CX-7 Single OSFP |
|---------|---------------------|-------------------|------------------|
| Max Bandwidth | 400Gb/s | 2x200Gb/s | 400Gb/s |
| Form Factor | QSFP112 | 2x QSFP112 | OSFP (Flat Top) |
| SerDes Lanes | 4 lanes | 4 lanes per port | 4 lanes |
| Lane Speed | 100G PAM4 | 50G PAM4 per port | 100G PAM4 |
| PCIe Gen | 5.0 x16 | 5.0 x16 | 5.0 x16 |
| Protocols | Ethernet, InfiniBand NDR | Ethernet, InfiniBand NDR200 | Ethernet, InfiniBand NDR |
| Variants | PCIe, OCP | PCIe, OCP | PCIe HHHL, OCP TSFF |

### Backward Compatibility

The QSFP112 connector is **backward compatible** with:
- **QSFP56:** 200G with 4x50G-PAM4
- **QSFP28:** 100G with 4x25G-NRZ
- **QSFP+:** Lower speeds

### Supported Cables and Optics

#### QSFP112 Cables (for QSFP112 variants)

**Direct Attach Copper (DAC):**
- QSFP112 400G DAC: 0.5m, 1m, 2m, 3m lengths
- QSFP112 200G DAC (for dual-port): 1m, 2m, 3m lengths
- Splitter cables: 400G QSFP112 to 2x200G QSFP56

**Active Optical Cables (AOC):**
- QSFP112 400G AOC: Up to 100m

**Optical Transceivers:**
- QSFP112 400G SR8 (multimode, 100m) - 8 parallel lanes
- QSFP112 400G DR4 (single-mode, 500m) - 4 lanes @ 100G PAM4
- QSFP112 400G FR4 (single-mode, 2km)
- QSFP112 400G LR4 (single-mode, 10km)
- QSFP112 200G SR4 (multimode, 100m) - 4 lanes @ 50G PAM4

#### OSFP Cables (for OSFP variants)

**Direct Attach Copper (DAC):**
- OSFP 400G DAC: 0.5m, 1m, 2m, 3m lengths
- OSFP Flat Top compatible passive copper

**Active Optical Cables (AOC):**
- OSFP 400G AOC: Up to 100m

**Optical Transceivers:**
- OSFP 400G SR8 (multimode, 100m) - 8 parallel lanes
- OSFP 400G DR4 (single-mode, 500m) - 4 lanes @ 100G PAM4
- OSFP 400G FR4 (single-mode, 2km)
- OSFP 400G LR4 (single-mode, 10km)

**Important Note:** ConnectX-7 OSFP variants use **flat-top OSFP modules** on the NIC side, which differs from switch-side modules. Ensure cable/transceiver compatibility with flat-top form factor.

### Example Part Numbers

**QSFP112 Variants:**
- **MCX75310AAS-NEAT:** ConnectX-7 VPI single-port QSFP112 NDR/400GbE
- **MCX75520AAS-NEAT:** ConnectX-7 VPI dual-port QSFP112 2x200GbE

**OSFP Variants:**
- **MCX75510AAS-NEAT:** ConnectX-7 VPI single-port OSFP NDR/400GbE (PCIe HHHL)
- **MCX75343AAS-NEAC1:** ConnectX-7 single-port OSFP NDR/400GbE (OCP 3.0 TSFF)
- **MCX75343AMS-NEAC:** ConnectX-7 single-port OSFP NDR/400GbE (OCP 3.0 TSFF, Multi-Host, Socket Direct)

---

## ConnectX-8 SuperNIC

### Overview
The ConnectX-8 SuperNIC delivers 800Gb/s throughput using 200G-PAM4 signaling and introduces PCIe Gen 6 support.

### Models

#### C8180 - Single OSFP
- **Speeds:** 800Gb/s or 2x400Gb/s (split mode)
- **Form Factor:** OSFP-RHS (Riding Heat Sink)
- **Host Interface:** PCIe 6.0 x16
- **SerDes Technology:** 200Gb/s PAM4 per lane

#### C8240 - Dual QSFP112
- **Speeds:** 2x400Gb/s
- **Form Factor:** 2x QSFP112
- **Host Interface:** PCIe 6.0 x16
- **SerDes Technology:** 100Gb/s PAM4 per lane

### Technical Specifications

| Feature | C8180 (OSFP) | C8240 (QSFP112) |
|---------|--------------|-----------------|
| Max Bandwidth | 800Gb/s | 2x400Gb/s |
| Form Factor | 1x OSFP-RHS | 2x QSFP112 |
| SerDes Lanes | 4 lanes | 4 lanes per port |
| Lane Speed | 200G PAM4 | 100G PAM4 |
| PCIe Gen | 6.0 x16 | 6.0 x16 |
| Protocols | Ethernet, InfiniBand XDR | Ethernet, InfiniBand XDR |

### Supported Cables and Optics

**Direct Attach Copper (DAC):**
- OSFP 800G straight-through DAC: 0.5m, 1m, 1.5m, 2m
- OSFP to 2x QSFP112 breakout DAC: 800G split to 2x400G (NVIDIA part: 980-9I80Q-00N02A for 2.5m)
- OSFP-RHS to OSFP-RHS DAC: Direct connection between ConnectX-8 adapters

**Active Cables:**
- OSFP 800G AEC (Active Electrical Cable): Up to 5m
- OSFP 800G AOC (Active Optical Cable): Up to 100m
- OSFP 800G ACC (Active Copper Cable): Medium reach

**Optical Transceivers:**
- OSFP224 800G DR4 (single-mode, 500m) - Part: MMA4A20-XM800
- OSFP224 800G SR8 (multimode, 50m) - Twin-port also available
- OSFP224 800G FR4 (single-mode, 2km)
- OSFP224 800G LR4 (single-mode, 10km)

**Note:** OSFP-RHS (Riding Heat Sink) and OSFP Flat Top are mechanically compatible. OSFP224 refers to 800G modules using 4x200G-PAM4 lanes.

### LPO (Linear Pluggable Optics)
ConnectX-8 supports low-power LPO transceivers that eliminate onboard DSP, reducing power consumption by up to 50% compared to traditional modules.

---

## ConnectX-9 SuperNIC

### Overview
The ConnectX-9 SuperNIC represents NVIDIA's next-generation networking solution, doubling the bandwidth to 1.6Tb/s. Expected availability: 2026 as part of the NVIDIA Vera Rubin platform.

### Specifications

| Feature | ConnectX-9 |
|---------|------------|
| Max Bandwidth | 1.6Tb/s |
| Expected Form Factor | OSFP (TBD - possibly OSFP-XD) |
| SerDes Technology | 224Gb/s PAM4 per lane (estimated) |
| PCIe Gen | 6.0 x48 lanes (3x16) |
| Protocols | Ethernet, InfiniBand (next-gen) |
| Availability | 2026 (Vera Rubin platform) |

### Key Features

- **6x Throughput Increase:** Compared to ConnectX-7
- **Advanced RDMA:** Next-generation RDMA capabilities
- **AI-Optimized:** Designed specifically for AI factory networks and GPU-to-GPU communication
- **Multi-Chip Architecture:** Can be packaged as multiple chips for 1.6T GPU interconnects

### Form Factor Considerations

The 1.6T speed may utilize:
- **OSFP-XD:** Extended density OSFP with 16 electrical lanes (potential for 16x100G or 8x200G)
- **Multiple OSFPs:** Dual 800G OSFP configuration
- **Custom High-Density Connector:** Purpose-built for AI infrastructure

### Expected Cables and Optics (Projected)

**Projected DAC/ACC:**
- 1.6T OSFP-XD straight-through cables
- 1.6T to 2x800G breakout cables
- 1.6T to 4x400G splitter cables

**Projected Optical Transceivers:**
- 1.6T DR8 or DR16 (single-mode)
- 1.6T SR16 (multimode)
- LPO versions for reduced power consumption

**Note:** Specifications are preliminary based on available announcements. Final specifications will be published closer to product release in 2026.

---

## BlueField-3 DPU

### Overview
BlueField-3 combines ConnectX-7 networking technology with an Arm-based SoC for data center infrastructure processing.

### Models

#### B3140H - Single-Port 400G
- **CPU:** 8x Arm Neoverse V2 cores
- **Memory:** 16GB DDR5
- **Network:** 1x QSFP112 - 400Gb/s Ethernet or NDR InfiniBand
- **Host Interface:** PCIe 5.0 x16

#### B3220 - Dual-Port 200G
- **CPU:** 16x Arm Neoverse V2 cores
- **Memory:** 32GB DDR5
- **Network:** 2x QSFP112 - 200Gb/s per port Ethernet or NDR200 InfiniBand
- **Host Interface:** PCIe 5.0 x16

### Technical Specifications

| Feature | B3140H | B3220 |
|---------|--------|-------|
| Arm Cores | 8 (Neoverse V2) | 16 (Neoverse V2) |
| Memory | 16GB DDR5 | 32GB DDR5 |
| Network Ports | 1x QSFP112 | 2x QSFP112 |
| Network Speed | 400Gb/s | 2x200Gb/s |
| SerDes Lanes | 4 lanes @ 100G PAM4 | 4 lanes @ 50G PAM4 per port |
| PCIe Gen | 5.0 x16 | 5.0 x16 |
| Protocols | Ethernet, InfiniBand NDR | Ethernet, InfiniBand NDR200 |

### Port Configuration Flexibility

BlueField-3 supports multiple port configurations:
- **1x 400Gb/s:** Four lanes of 100G-PAM4
- **2x 200Gb/s:** Four lanes of 50G-PAM4 per port
- **4x 100Gb/s:** Breakout configuration
- **Lower speeds:** 25G, 50G, 100G as needed

### Supported Cables and Optics

BlueField-3 uses the same ConnectX-7 networking technology, so it supports the same optics and cables as ConnectX-7:

**Direct Attach Copper (DAC):**
- QSFP112 400G DAC (B3140H)
- QSFP112 200G DAC (B3220)
- Breakout and splitter cables

**Optical Transceivers:**
- QSFP112 400G SR8, DR4, FR4, LR4 (B3140H)
- QSFP112 200G SR4, DR4 (B3220)
- MMA1Z00-NS400 compatible: 400GBASE-SR4 QSFP112

---

## BlueField-4 DPU

### Overview
BlueField-4 combines NVIDIA Grace CPU with ConnectX-9 networking technology (not ConnectX-8), delivering 800Gb/s networking. Expected availability: Early 2026.

### Specifications

| Feature | BlueField-4 |
|---------|-------------|
| CPU | 64x Arm Neoverse V2 cores |
| Memory | 128GB LPDDR5 |
| Storage | 512GB on-board SSD |
| Cache | 114MB shared L3 |
| Transistors | 64 billion |
| Network Speed | 800Gb/s |
| Typical Config | 2x400Gb/s links (bi-directional) |
| Host Interface | PCIe 6.0 x16 |
| Availability | Q1 2026 (Vera Rubin platform) |

### Key Improvements over BlueField-3

- **6x Compute Power:** 64 cores vs. 16 cores (compared to B3220)
- **2x Network Bandwidth:** 800Gb/s vs. 400Gb/s
- **8x Memory:** 128GB vs. 16GB (compared to B3140H)
- **PCIe Gen 6:** Doubled host interface bandwidth

### GPU-to-GPU Networking

For GPU interconnect in the Rubin platform, BlueField-4 can leverage multi-chip ConnectX-9 configurations to achieve **1.6Tb/s per GPU**.

### Expected Cables and Optics

BlueField-4 with 800Gb/s networking will likely support:

**For 800G Single-Port Configuration:**
- OSFP 800G DAC/ACC/AOC cables
- OSFP224 800G optical transceivers (DR4, SR8, FR4, LR4)

**For 2x400G Dual-Port Configuration:**
- QSFP112 400G cables and optics
- Same as ConnectX-7 transceivers

**Note:** Final specifications pending product release documentation in 2026.

---

## Form Factors and Connectors

### QSFP Family Evolution

#### QSFP28 (Quad Small Form-factor Pluggable 28)
- **Lanes:** 4 electrical lanes
- **Lane Speed:** Up to 25G NRZ (28Gb/s including encoding)
- **Total Bandwidth:** 100Gb/s
- **Typical Use:** 100GbE, 40GbE, EDR InfiniBand
- **Connector:** QSFP28 (38-pin)

#### QSFP56 (Quad Small Form-factor Pluggable 56)
- **Lanes:** 4 electrical lanes
- **Lane Speed:** Up to 50G PAM4 (56Gb/s including encoding)
- **Total Bandwidth:** 200Gb/s
- **Typical Use:** 200GbE, HDR InfiniBand
- **Connector:** QSFP56 (38-pin, backward compatible with QSFP28)

#### QSFP112 (Quad Small Form-factor Pluggable 112)
- **Lanes:** 4 electrical lanes (8 optical lanes possible)
- **Lane Speed:** Up to 100G PAM4 (112Gb/s including encoding)
- **Total Bandwidth:** 400Gb/s
- **Typical Use:** 400GbE, NDR InfiniBand
- **Connector:** QSFP112 (38-pin, backward compatible with QSFP56/QSFP28)
- **Used In:** ConnectX-7, BlueField-3, ConnectX-8 C8240

#### QSFP-DD (Double Density)
- **Lanes:** 8 electrical lanes
- **Lane Speed:** Up to 50G PAM4
- **Total Bandwidth:** 400Gb/s
- **Note:** Used in Ethernet switches but **NOT in ConnectX-7 or BlueField-3**

### OSFP Family

#### OSFP (Octal Small Form Factor Pluggable)
- **Lanes:** 8 electrical lanes
- **Lane Speed:** Up to 100G PAM4 per lane
- **Total Bandwidth:** 800Gb/s
- **Typical Use:** 800GbE, XDR InfiniBand
- **Connector:** OSFP (74-pin)
- **Used In:** ConnectX-8 C8180 (OSFP-RHS variant)

#### OSFP224
- **Technology:** OSFP using 200G PAM4 signaling
- **Lanes:** 4 electrical lanes @ 200G PAM4 = 800Gb/s
- **Note:** "224" refers to 224Gb/s per lane with encoding overhead
- **Used In:** ConnectX-8 800G optical transceivers

#### OSFP-RHS (Riding Heat Sink)
- **Description:** OSFP variant with integrated heat sink for server NIC applications
- **Mechanical:** Compatible with standard OSFP and OSFP Flat Top
- **Thermal:** Optimized thermal interface for high-density server environments
- **Used In:** ConnectX-8 C8180

#### OSFP-XD (Extended Density) - Emerging
- **Lanes:** 16 electrical lanes (projected)
- **Lane Speed:** Up to 100G or 200G PAM4 per lane
- **Total Bandwidth:** 1.6Tb/s - 3.2Tb/s potential
- **Typical Use:** Future 1.6T/3.2T networking
- **Status:** Emerging standard for next-generation speeds
- **Likely Use:** ConnectX-9 (expected 2026)

### SFP Family (Legacy/Lower Speed)

#### SFP28
- **Lanes:** 1 electrical lane
- **Lane Speed:** 25G NRZ
- **Total Bandwidth:** 25Gb/s
- **Used In:** ConnectX-6 Lx

### Form Factor Comparison Table

| Form Factor | Lanes | Max Lane Speed | Total BW | Backward Compatible | NVIDIA NICs Using It |
|-------------|-------|----------------|----------|---------------------|----------------------|
| SFP28 | 1 | 25G NRZ | 25Gb/s | SFP+ | ConnectX-6 Lx |
| QSFP28 | 4 | 25G NRZ | 100Gb/s | QSFP+ | ConnectX-6 |
| QSFP56 | 4 | 50G PAM4 | 200Gb/s | QSFP28, QSFP+ | ConnectX-6 Dx/VPI |
| QSFP112 | 4-8 | 100G PAM4 | 400Gb/s | QSFP56, QSFP28 | ConnectX-7, BF-3, CX-8 C8240 |
| QSFP-DD | 8 | 50G PAM4 | 400Gb/s | QSFP28 | Not used in ConnectX/BF |
| OSFP (Flat Top) | 4 | 100G PAM4 | 400Gb/s | No | ConnectX-7 (OSFP variants) |
| OSFP | 8 | 100G PAM4 | 800Gb/s | No | - |
| OSFP-RHS | 8 | 100G PAM4 | 800Gb/s | OSFP Flat Top | ConnectX-8 C8180 |
| OSFP224 | 4 | 200G PAM4 | 800Gb/s | No | ConnectX-8 C8180 transceivers |
| OSFP-XD | 16 | 100-200G PAM4 | 1.6-3.2Tb/s | TBD | ConnectX-9 (projected) |

---

## Signaling Technologies

### NRZ (Non-Return-to-Zero)

**Description:** Simple two-level signaling (high/low voltage) representing binary 1 and 0.

**Characteristics:**
- **Bits per Symbol:** 1 bit per symbol
- **Voltage Levels:** 2 levels
- **Speed Range:** Up to 28Gb/s per lane (25G data + encoding overhead)
- **Advantages:** Simple, proven technology; lower power consumption
- **Disadvantages:** Limited to lower speeds due to signal integrity challenges

**NVIDIA Usage:**
- **10G NRZ:** 10GbE (SFP+)
- **25G NRZ:** 25GbE (SFP28), 100GbE (4x25G QSFP28)
- **28G NRZ:** EDR InfiniBand (4x25G = 100Gb/s)

**ConnectX Products Using NRZ:**
- ConnectX-6 Lx: 25G NRZ
- ConnectX-6 Dx/VPI: Backward compatibility with 25G NRZ

### PAM4 (Pulse Amplitude Modulation 4-Level)

**Description:** Four-level signaling encoding 2 bits per symbol using four distinct voltage levels.

**Characteristics:**
- **Bits per Symbol:** 2 bits per symbol
- **Voltage Levels:** 4 levels
- **Data Efficiency:** Doubles data rate compared to NRZ at same baud rate
- **Advantages:** Higher data rates without increasing frequency
- **Disadvantages:** More susceptible to noise; requires better signal integrity; higher power consumption for DSP

#### PAM4 Speed Variants

##### 50G PAM4 (56Gb/s with encoding)
- **Data Rate:** 50Gb/s per lane
- **Total Bandwidth:** 200Gb/s (4 lanes)
- **Form Factor:** QSFP56
- **Applications:** 200GbE, HDR InfiniBand (200Gb/s)
- **NVIDIA Products:** ConnectX-6 Dx/VPI, ConnectX-7 (backward compat)

##### 100G PAM4 (112Gb/s with encoding)
- **Data Rate:** 100Gb/s per lane
- **Total Bandwidth:** 400Gb/s (4 lanes) or 800Gb/s (8 lanes)
- **Form Factor:** QSFP112, OSFP
- **Applications:** 400GbE, NDR InfiniBand, 800GbE
- **NVIDIA Products:** ConnectX-7 (native), ConnectX-8 C8240, BlueField-3

##### 200G PAM4 (224Gb/s with encoding)
- **Data Rate:** 200Gb/s per lane
- **Total Bandwidth:** 800Gb/s (4 lanes) or 1.6Tb/s (8 lanes)
- **Form Factor:** OSFP224, OSFP-RHS
- **Applications:** 800GbE, XDR InfiniBand
- **NVIDIA Products:** ConnectX-8 C8180

##### 224G PAM4 (Projected for ConnectX-9)
- **Data Rate:** ~224Gb/s per lane (projected)
- **Total Bandwidth:** ~1.6Tb/s (8 lanes) or ~3.2Tb/s (16 lanes)
- **Form Factor:** OSFP-XD (projected)
- **Applications:** Next-gen 1.6T/3.2T Ethernet, future InfiniBand
- **NVIDIA Products:** ConnectX-9 (expected 2026)

### Comparison Table

| Technology | Bits/Symbol | Lane Speed | 4-Lane BW | 8-Lane BW | Power | Signal Integrity |
|------------|-------------|------------|-----------|-----------|-------|------------------|
| 10G NRZ | 1 | 10Gb/s | 40Gb/s | 80Gb/s | Low | Excellent |
| 25G NRZ | 1 | 25Gb/s | 100Gb/s | 200Gb/s | Low | Good |
| 50G PAM4 | 2 | 50Gb/s | 200Gb/s | 400Gb/s | Medium | Good |
| 100G PAM4 | 2 | 100Gb/s | 400Gb/s | 800Gb/s | Medium-High | Moderate |
| 200G PAM4 | 2 | 200Gb/s | 800Gb/s | 1.6Tb/s | High | Challenging |

### Encoding Overhead

All signaling technologies include encoding overhead for clock recovery and error correction:

- **64b/66b Encoding:** Used with NRZ and PAM4
  - Overhead: ~3.125%
  - Example: 25G data rate = 25.78125G baud (often referred to as 28G)
  - Example: 50G data rate = 51.5625G baud (often referred to as 56G)
  - Example: 100G data rate = 103.125G baud (often referred to as 112G)
  - Example: 200G data rate = 206.25G baud (often referred to as 224G)

---

## NVIDIA LinkX Optics and DACs

NVIDIA's LinkX brand provides cables and transceivers specifically designed and tested for ConnectX and BlueField products.

### LinkX Product Categories

#### 1. Direct Attach Copper (DAC) - Passive
- **Description:** Copper twinax cables with integrated transceivers (passive electronics)
- **Reach:** Up to 5 meters (typically 1-3m for high speeds)
- **Advantages:** Low cost, low power consumption, low latency
- **Disadvantages:** Limited reach, bulky at high port density
- **Use Cases:** Top-of-Rack (ToR) connections, server-to-switch

#### 2. Active Electrical Cable (AEC)
- **Description:** Copper cables with active signal conditioning electronics
- **Reach:** Up to 7 meters
- **Advantages:** Longer reach than passive DAC, lower power than AOC
- **Use Cases:** Extended rack connections

#### 3. Active Copper Cable (ACC)
- **Description:** Enhanced active copper with advanced signal processing
- **Reach:** Up to 10 meters
- **Advantages:** Even longer copper reach, cost-effective
- **Use Cases:** Middle-of-Row (MoR) connections

#### 4. Active Optical Cable (AOC)
- **Description:** Integrated optical transceivers with fiber cable
- **Reach:** Up to 100 meters (some up to 300m)
- **Advantages:** Light weight, flexible, immune to EMI
- **Disadvantages:** Higher cost than copper, not field-repairable
- **Use Cases:** Cross-rack, end-of-row connections

#### 5. Optical Transceivers
- **Description:** Pluggable optical modules used with fiber patch cables
- **Reach:** 100m to 100km+ depending on type
- **Advantages:** Field-replaceable, flexible distance options
- **Disadvantages:** Higher cost, requires separate fiber management
- **Use Cases:** Data center interconnect, campus networks, long-reach

### LinkX Cable Types by Speed

#### 100G Cables (ConnectX-6)

**QSFP28 100G DAC:**
- Part Number Pattern: MCP1600-X00X (X = length code)
- Lengths: 0.5m, 1m, 2m, 3m, 5m
- Connector: QSFP28 to QSFP28

**QSFP28 100G AOC:**
- Part Number Pattern: MFA1A00-XXX (XX = length code)
- Lengths: 5m, 10m, 20m, 30m, 50m, 100m
- Technology: Multimode optical

**QSFP28 to 4x SFP28 Breakout DAC (100G to 4x25G):**
- Part Number Pattern: MCP7Y00-X00X
- Use Case: 100G switch port to four 25G servers

#### 200G Cables (ConnectX-6 Dx/VPI)

**QSFP56 200G DAC:**
- Part Number Pattern: MCP1650-X00X
- Example: MCP1650-H00AE30 (0.5m)
- Lengths: 0.5m, 1m, 2m, 3m
- Connector: QSFP56 to QSFP56

**QSFP56 200G AOC:**
- Part Number Pattern: MFS1S00-X00X
- Lengths: 5m, 10m, 30m, 50m, 100m

**QSFP56 to 2x QSFP56 Breakout (200G to 2x100G):**
- Part Number Pattern: MCA7J50-X00X
- Example: MCA7J50-H003R (3m active)

#### 400G Cables (ConnectX-7, BlueField-3)

**QSFP112 400G DAC:**
- Part Number Pattern: MCP4Y00-X00X
- Example: MCP4Y10-NO01 (1m)
- Lengths: 0.5m, 1m, 2m, 3m
- Connector: QSFP112 to QSFP112 Flat Top

**QSFP112 400G AOC:**
- Lengths: 5m, 10m, 20m, 30m, 50m, 100m
- Technology: Parallel multimode optical

**QSFP112 to 2x QSFP56 Splitter (400G to 2x200G):**
- Use Case: 400G NIC to two 200G switches

**QSFP112 to 4x QSFP56 Breakout (400G to 4x100G):**
- Use Case: 400G port to four 100G connections

#### 800G Cables (ConnectX-8)

**OSFP 800G Straight-Through DAC:**
- Connector: OSFP-RHS to OSFP-RHS or OSFP Flat Top
- Lengths: 0.5m, 1m, 1.5m, 2m, 2.5m
- Technology: Passive copper twinax

**OSFP to 2x QSFP112 Splitter DAC (800G to 2x400G):**
- Part Number: 980-9I80Q-00N02A (2.5m example)
- Use Case: ConnectX-8 800G to two 400G devices
- Technology: Passive copper breakout

**OSFP 800G AEC:**
- Lengths: 3m, 5m
- Technology: Active copper

**OSFP 800G AOC:**
- Lengths: 10m, 20m, 30m, 50m, 100m
- Technology: Parallel multimode optical

### LinkX Optical Transceivers

#### Multimode (Short Reach - SR)

**100G QSFP28 SR4:**
- Wavelength: 850nm VCSEL
- Fiber: OM3 (70m), OM4 (100m), OM5 (150m)
- Lanes: 4x 25G NRZ
- Connector: MPO-12 (MTP)

**200G QSFP56 SR4:**
- Wavelength: 850nm VCSEL
- Fiber: OM3 (70m), OM4 (100m)
- Lanes: 4x 50G PAM4
- Connector: MPO-12 (MTP)

**400G QSFP112 SR8:**
- Wavelength: 850nm VCSEL
- Fiber: OM3 (50m), OM4 (100m)
- Lanes: 8x 50G PAM4 (requires 2x MPO-12 or 1x MPO-16)
- Connector: 2x MPO-12 or MPO-16

**800G OSFP224 SR8:**
- Part Number Pattern: MMS4X00-NS
- Example: MMA4Z00-NS (800G Twin-port OSFP 2x400G SR8)
- Wavelength: 850nm VCSEL
- Fiber: OM4 (50m)
- Lanes: 8x 100G PAM4
- Connector: 2x MPO-12 or MPO-16

#### Single-Mode (DR - Data Rate, FR - Fast Rate, LR - Long Reach)

**100G QSFP28 DR1:**
- Wavelength: 1310nm
- Reach: 500m (SMF)
- Lanes: 1x 100G PAM4
- Connector: LC duplex

**100G QSFP28 LR4:**
- Wavelength: 4x CWDM around 1310nm
- Reach: 10km (SMF)
- Lanes: 4x 25G NRZ with WDM
- Connector: LC duplex

**200G QSFP56 DR4:**
- Wavelength: 1310nm
- Reach: 500m (SMF)
- Lanes: 4x 50G PAM4
- Connector: MPO-12 (MTP)

**400G QSFP112 DR4:**
- Wavelength: 1310nm
- Reach: 500m (SMF)
- Lanes: 4x 100G PAM4
- Connector: MPO-12 (MTP)

**400G QSFP112 FR4:**
- Wavelength: 4x CWDM around 1310nm
- Reach: 2km (SMF)
- Lanes: 4x 100G PAM4 with WDM
- Connector: LC duplex

**400G QSFP112 LR4:**
- Wavelength: 4x LAN-WDM
- Reach: 10km (SMF)
- Lanes: 4x 100G PAM4 with WDM
- Connector: LC duplex

**800G OSFP224 DR4:**
- Part Number: MMA4A20-XM800
- Wavelength: 1310nm
- Reach: 500m (SMF)
- Lanes: 4x 200G PAM4
- Connector: MPO-12 (MTP)
- Form: OSFP224 Riding Heat Sink or Flat Top

**800G OSFP224 FR4:**
- Wavelength: 4x CWDM around 1310nm
- Reach: 2km (SMF)
- Lanes: 4x 200G PAM4 with WDM
- Connector: LC duplex

**800G OSFP224 LR4:**
- Wavelength: 4x LAN-WDM
- Reach: 10km (SMF)
- Lanes: 4x 200G PAM4 with WDM
- Connector: LC duplex

#### Linear Pluggable Optics (LPO)

LPO transceivers eliminate onboard DSP (Digital Signal Processing), moving the signal processing to the NIC/switch ASIC. This reduces power consumption significantly.

**Benefits:**
- **50% Power Reduction:** Compared to traditional modules
- **Lower Cost:** Simpler electronics
- **Lower Latency:** No DSP processing delay

**Supported Speeds:**
- 400G QSFP112 LPO
- 800G OSFP224 LPO

**Considerations:**
- Requires compatible host (ConnectX-8 and newer support LPO)
- Best for short-medium reach (typically DR4 style)

### LinkX Quality Assurance

- **100% Tested:** All LinkX cables tested on actual NVIDIA switches and NICs
- **Signal Integrity:** Verified in live GPU and switching systems
- **Backward Compatibility Validated:** QSFP112 modules tested with QSFP56/QSFP28
- **Thermal Testing:** High-temperature operation validated

### Important Notes on NVIDIA Support

From NVIDIA documentation:
> "NVIDIA does not support InfiniBand cables or modules not qualified or approved by NVIDIA."

For **Ethernet applications**, NVIDIA is more flexible with third-party modules, but InfiniBand protocols require NVIDIA-approved transceivers for support eligibility.

---

## Third-Party Compatible Optics

While NVIDIA recommends using LinkX products, several third-party manufacturers produce compatible transceivers and cables that are tested and validated.

### Major Third-Party Manufacturers

#### Manufacturing Chain
- **Component Suppliers:** Avago, Finisar (II-VI), Lumentum, Broadcom
- **OEM/Compatible Vendors:** FS.com, NADDOD, Fiberstore, EdgeOptic, ProLabs, EDGE

**Key Fact:** Most transceivers (OEM and third-party) are manufactured using the same core components from a small number of qualified suppliers.

### Third-Party Testing and Validation

#### FS.com
- **Testing:** Maintains NVIDIA original devices in testing lab
- **Validation:** Tests all HDR, NDR, XDR InfiniBand products on NVIDIA hardware
- **Compatibility Claims:** 100% compatibility for ConnectX-6, ConnectX-7
- **Quality Control:** Tests each product before shipment
- **Documentation:** Publishes compatibility lists for ConnectX NICs

**Example Products:**
- 100G QSFP28 compatible with ConnectX-6: DAC, AOC, SR4, LR4
- 200G QSFP56 compatible with ConnectX-6 Dx: DAC, AOC, SR4, DR4
- 400G QSFP112 compatible with ConnectX-7/BlueField-3: DAC, AOC, SR8, DR4
- 800G OSFP compatible with ConnectX-8: Breakout DAC, SR8, DR4

#### NADDOD
- **Focus:** InfiniBand and high-speed Ethernet
- **Testing:** Validated on NVIDIA ConnectX platforms
- **Specialization:** OSFP and QSFP112 products for 400G/800G

**Example Products:**
- NVIDIA MMA4A20-XM800 Compatible: 800G DR4 OSFP224
- NVIDIA MMA1Z00-NS400 Compatible: 400GBASE-SR4 QSFP112
- ConnectX-7 compatible QSFP112 transceivers

#### EdgeOptic / EDGE
- **Product Range:** DAC, AOC, and breakout cables
- **NVIDIA Focus:** Mellanox-compatible product line
- **Applications:** ConnectX adapters and Spectrum switches

### Third-Party DAC Cables

#### 100G QSFP28 DAC (ConnectX-6)
- **FS.com Part Examples:**
  - QSFP28 100G passive: 0.5m, 1m, 2m, 3m, 5m
  - QSFP28 to 4x SFP28 breakout: 100G to 4x25G
- **Compatibility:** ConnectX-6, ConnectX-7 (backward compat)

#### 200G QSFP56 DAC (ConnectX-6 Dx/VPI)
- **FS.com Part Examples:**
  - Part: 205043 - MCP1650-H00AE30 compatible (0.5m)
  - Part: 166186 - MCA7J50-H003R compatible (3m breakout to 2x100G)
- **InfiniBand:** HDR compatible
- **Compatibility:** ConnectX-6 Dx/VPI, ConnectX-7 (backward compat)

#### 400G QSFP112 DAC (ConnectX-7, BlueField-3)
- **FS.com Part Examples:**
  - QSFP112 400G passive: 0.5m, 1m, 2m, 3m
  - Part: 219559 - MCP4Y10-NO01 compatible (1m)
  - QSFP112 to 4x QSFP56 breakout: 400G to 4x100G HDR
- **InfiniBand:** NDR compatible
- **Compatibility:** ConnectX-7, BlueField-3

#### 800G OSFP DAC (ConnectX-8)
- **FS.com Part Examples:**
  - Part: 205005 - OSFP to 2x OSFP breakout (0.5m, 800G to 2x400G)
  - Part: 224827 - OSFP Finned to 4x QSFP56 (400G to 4x100G)
- **InfiniBand:** XDR compatible
- **Compatibility:** ConnectX-8 C8180

### Third-Party Optical Transceivers

#### 100G QSFP28 Optics
- **FS.com 100GBASE-SR4:** 850nm, 70-100m (OM3/OM4)
- **FS.com 100GBASE-LR4:** 1310nm LAN-WDM, 10km
- **FS.com 100GBASE-DR1:** 1310nm, 500m

#### 200G QSFP56 Optics
- **Third-party SR4:** 850nm, OM4 100m, 4x50G PAM4
- **Third-party DR4:** 1310nm, SMF 500m, 4x50G PAM4

#### 400G QSFP112 Optics
- **FS.com 400GBASE-SR8:** 850nm VCSEL, OM4 100m, 8x50G PAM4
- **NADDOD MMA1Z00-NS400 Compatible:** 400GBASE-SR4, QSFP112
- **Third-party DR4:** 1310nm, SMF 500m, 4x100G PAM4
- **Third-party FR4:** 1310nm CWDM, SMF 2km
- **Third-party LR4:** LAN-WDM, SMF 10km

#### 800G OSFP224 Optics
- **NADDOD MMA4A20-XM800 Compatible:**
  - 800G DR4 OSFP224
  - 4x200G-PAM4, 1310nm, SMF 500m
  - Riding Heat Sink or Flat Top versions
- **FS.com Part 344985:**
  - 800GBASE-DR4 OSFP224 Flat Top
  - PAM4 1310nm, 500m
  - MPO-12/APC SMF
  - InfiniBand XDR compatible

### Warranty and Support Considerations

#### Warranty Protection
- **Network Equipment:** Installing third-party transceivers **does NOT void** network equipment warranties
- **Industry Standard:** Equipment manufacturers cannot void warranties based solely on third-party optics
- **NVIDIA Position:** NVIDIA recommends LinkX products but does not void NIC warranties for third-party optics in Ethernet mode

#### Support Considerations
- **InfiniBand:** NVIDIA support may require NVIDIA-approved modules for InfiniBand troubleshooting
- **Ethernet:** More flexible; third-party transceivers generally supported
- **Troubleshooting:** For support cases, having NVIDIA LinkX cables for testing may expedite resolution

#### Testing Recommendation
When using third-party optics:
1. **Verify Compatibility:** Check vendor's published compatibility list
2. **Request Test Reports:** Ask for validation testing data on NVIDIA hardware
3. **Pilot Testing:** Test small quantities before bulk purchase
4. **Monitor Link Quality:** Use NVIDIA mlx tools to verify signal quality and error rates
5. **Performance Validation:** Run throughput and latency tests

### Cost Considerations

Third-party optics typically offer **40-70% cost savings** compared to OEM modules:

| Product Type | OEM Cost (Est.) | Third-Party Cost (Est.) | Savings |
|--------------|-----------------|-------------------------|---------|
| QSFP28 100G SR4 | $300-500 | $100-200 | 50-66% |
| QSFP56 200G SR4 | $800-1200 | $250-450 | 60-70% |
| QSFP112 400G SR8 | $1500-2500 | $500-1000 | 60-67% |
| OSFP224 800G DR4 | $3000-5000 | $1200-2000 | 50-60% |
| QSFP28 100G DAC 3m | $100-150 | $40-70 | 50-60% |
| QSFP112 400G DAC 2m | $250-400 | $100-180 | 50-60% |

*Note: Prices are approximate and vary by volume, vendor, and market conditions.*

---

## Compatibility Matrix

### ConnectX NIC Cable Compatibility

| NIC Model | Form Factor | Native Speed | Compatible Cables/Optics | Backward Compatible Cables |
|-----------|-------------|--------------|--------------------------|----------------------------|
| **ConnectX-6 Lx** | SFP28 | 25G | SFP28 25G (DAC/AOC/SR/LR) | SFP+ 10G |
| **ConnectX-6 Dx** | QSFP56 | 100G/200G | QSFP56 200G (DAC/AOC/SR4/DR4)<br>QSFP28 100G (DAC/AOC/SR4/LR4) | QSFP28 100G<br>QSFP+ 40G |
| **ConnectX-6 VPI** | QSFP56 | 100G/200G | QSFP56 200G HDR IB<br>QSFP56 200GbE<br>QSFP28 100G EDR IB | QSFP28 100G<br>QSFP+ 40G |
| **ConnectX-7 Single QSFP112** | QSFP112 | 400G | QSFP112 400G (DAC/AOC/SR8/DR4/FR4/LR4) | QSFP56 200G<br>QSFP28 100G |
| **ConnectX-7 Single OSFP** | OSFP Flat Top | 400G | OSFP 400G (DAC/AOC/SR8/DR4/FR4/LR4) | No |
| **ConnectX-7 Dual** | 2x QSFP112 | 2x200G | QSFP112 200G per port<br>QSFP56 200G (native) | QSFP28 100G per port |
| **ConnectX-8 C8180** | OSFP-RHS | 800G or 2x400G | OSFP 800G (DAC/AEC/AOC)<br>OSFP224 800G (SR8/DR4/FR4/LR4)<br>OSFP to 2xQSFP112 splitter | Limited - OSFP not backward compat with QSFP |
| **ConnectX-8 C8240** | 2x QSFP112 | 2x400G | QSFP112 400G per port | QSFP56 200G<br>QSFP28 100G |
| **ConnectX-9** | OSFP-XD (TBD) | 1.6T | TBD (OSFP-XD 1.6T, breakouts) | TBD - Details pending 2026 release |

### BlueField DPU Cable Compatibility

| DPU Model | Form Factor | Native Speed | Compatible Cables/Optics | Backward Compatible Cables |
|-----------|-------------|--------------|--------------------------|----------------------------|
| **BlueField-3 B3140H** | QSFP112 | 400G | QSFP112 400G (DAC/AOC/SR8/DR4/FR4/LR4) | QSFP56 200G<br>QSFP28 100G |
| **BlueField-3 B3220** | 2x QSFP112 | 2x200G | QSFP112 200G per port<br>QSFP56 200G | QSFP28 100G per port |
| **BlueField-4** | OSFP (TBD) | 800G / 2x400G | TBD - OSFP 800G cables/optics | TBD - Details pending 2026 |

### Port Configuration Flexibility

#### ConnectX-7 QSFP112 and BlueField-3

| Configuration | Lanes | Speed per Lane | Use Case |
|---------------|-------|----------------|----------|
| 1x 400G | 4 @ 100G PAM4 | 100G PAM4 | Single 400GbE or NDR InfiniBand |
| 2x 200G | 4 @ 50G PAM4 per port | 50G PAM4 | Dual 200GbE or NDR200 InfiniBand |
| 4x 100G | 1 @ 100G PAM4 per port | 100G PAM4 | Breakout to four 100GbE ports |
| 4x 50G | 1 @ 50G PAM4 per port | 50G PAM4 | Backward compat or breakout |
| 4x 25G | 1 @ 25G NRZ per port | 25G NRZ | Backward compat to QSFP28 |

#### ConnectX-7 OSFP

| Configuration | Lanes | Speed per Lane | Use Case |
|---------------|-------|----------------|----------|
| 1x 400G | 4 @ 100G PAM4 | 100G PAM4 | Single 400GbE or NDR InfiniBand |
| 1x 200G | 4 @ 50G PAM4 | 50G PAM4 | Single 200GbE (if supported) |

#### ConnectX-8 C8180 (OSFP-RHS)

| Configuration | Lanes | Speed per Lane | Use Case |
|---------------|-------|----------------|----------|
| 1x 800G | 4 @ 200G PAM4 | 200G PAM4 | Single 800GbE or XDR InfiniBand |
| 2x 400G | 4 @ 100G PAM4 split | 100G PAM4 | Split to two 400G ports via breakout cable |

### Interoperability Matrix

| NIC/DPU Speed | Switch Port Speed | Cable/Optic Solution |
|---------------|-------------------|----------------------|
| CX-6 100G | 100G QSFP28 | QSFP28 100G DAC/AOC/SR4/LR4 |
| CX-6 Dx 200G | 200G QSFP56 | QSFP56 200G DAC/AOC/SR4/DR4 |
| CX-6 Dx 100G | 100G QSFP28 | QSFP28 100G (backward compat) |
| CX-7 400G | 400G QSFP112 | QSFP112 400G DAC/AOC/SR8/DR4 |
| CX-7 200G | 200G QSFP56 | QSFP56 200G (backward compat) |
| CX-7 400G | 2x 200G QSFP56 | QSFP112 to 2xQSFP56 splitter cable |
| CX-8 800G | 800G OSFP | OSFP 800G DAC/AOC/DR4 |
| CX-8 800G | 2x 400G QSFP112 | OSFP to 2xQSFP112 splitter (980-9I80Q-00N02A) |
| CX-8 C8240 400G | 400G QSFP112 | QSFP112 400G DAC/AOC/SR8/DR4 |
| BF-3 B3140H 400G | 400G QSFP112 | QSFP112 400G (same as CX-7) |
| BF-3 B3220 200G | 200G QSFP56 | QSFP56 200G or QSFP112 200G |

### NVIDIA Switch Compatibility

| Switch Series | Port Speeds | Compatible NICs | InfiniBand Support |
|---------------|-------------|-----------------|-------------------|
| Spectrum-2 | 100G, 200G | CX-6, CX-7 (backward) | EDR, HDR |
| Spectrum-3 | 200G, 400G | CX-6 Dx, CX-7, BF-3 | HDR |
| Spectrum-4 | 400G | CX-7, CX-8 C8240, BF-3 | NDR |
| Quantum-2 | 400G | CX-7, BF-3 | NDR InfiniBand |
| Quantum-X800 | 800G | CX-8 C8180 | XDR InfiniBand (400G NDR compat) |

---

## Appendix: Quick Reference Tables

### Speed and Form Factor Quick Reference

| Speed | Form Factor | Lane Config | Signaling | NICs Using It |
|-------|-------------|-------------|-----------|---------------|
| 25G | SFP28 | 1x 25G | NRZ | CX-6 Lx |
| 100G | QSFP28 | 4x 25G | NRZ | CX-6 |
| 200G | QSFP56 | 4x 50G | PAM4 | CX-6 Dx/VPI |
| 400G | QSFP112 | 4x 100G | PAM4 | CX-7 QSFP112, BF-3, CX-8 C8240 |
| 400G | OSFP Flat Top | 4x 100G | PAM4 | CX-7 OSFP |
| 800G | OSFP-RHS | 4x 200G | PAM4 | CX-8 C8180 |
| 1.6T | OSFP-XD (TBD) | 8-16x | PAM4 | CX-9 (2026) |

### Optics Type Quick Reference

| Optic Type | Wavelength | Fiber Type | Typical Reach | Use Case |
|------------|------------|------------|---------------|----------|
| **SR** (Short Reach) | 850nm | Multimode (OM3/OM4) | 70-100m | Intra-rack, ToR |
| **DR** (Data Rate) | 1310nm | Single-mode | 500m | Inter-rack, MoR |
| **FR** (Fast Rate) | 1310nm CWDM | Single-mode | 2km | Campus, small DC |
| **LR** (Long Reach) | LAN-WDM | Single-mode | 10km | Data center interconnect |
| **ER** (Extended) | 1550nm | Single-mode | 40km | Metro networks |
| **ZR** (Ultra-long) | Coherent | Single-mode | 80-120km | DCI, long-haul |

### Cable Type Selection Guide

| Distance | Best Option | Pros | Cons |
|----------|-------------|------|------|
| 0.5-3m | Passive DAC | Lowest cost, low latency, low power | Bulky, heavy |
| 3-5m | Passive DAC | Low cost, no power | Very bulky |
| 5-7m | AEC | Better than DAC at distance | Higher cost than DAC |
| 7-10m | ACC | Longer copper reach | Higher cost |
| 10-100m | AOC | Lightweight, flexible | Higher cost, not repairable |
| 100m-500m | SR/DR Optics | Field-replaceable | Two parts (module + fiber) |
| 500m-10km | FR/LR Optics | Long reach | Higher cost |
| 10km+ | LR/ER/ZR | Very long reach | Expensive |

### Vendor Contact Information

**NVIDIA Networking:**
- Website: https://www.nvidia.com/en-us/networking/
- Documentation: https://docs.nvidia.com/networking/
- LinkX Products: https://www.nvidia.com/en-us/networking/interconnect/

**Third-Party Vendors:**
- **FS.com:** https://www.fs.com (NVIDIA/Mellanox compatible section)
- **NADDOD:** https://www.naddod.com (NVIDIA networking products)
- **EdgeOptic:** https://edgeoptic.com (Mellanox cables)

---

## Document Maintenance

This document should be updated as:
- New ConnectX models are released
- ConnectX-9 and BlueField-4 specifications finalize (expected Q1 2026)
- New optics standards emerge (e.g., OSFP-XD specifications)
- Third-party compatibility lists expand
- Pricing and availability change

**Contribution:** To suggest updates or corrections, please contact the HedgeHog  project maintainers.

---

## References

1. NVIDIA ConnectX Product Datasheets (nvidia.com)
2. NVIDIA BlueField DPU Documentation (docs.nvidia.com)
3. NVIDIA LinkX Cable and Transceiver Guides (docs.nvidia.com/networking)
4. Lenovo ThinkSystem Product Guides (lenovopress.lenovo.com)
5. FS.com Compatibility Documentation (community.fs.com)
6. NADDOD Technical Blog (naddod.com/blog)
7. Industry Standards: IEEE 802.3, InfiniBand Trade Association

---

**Document End**
