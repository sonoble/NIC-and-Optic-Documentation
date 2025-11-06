# Broadcom Thor Network Interface Cards Reference Guide

## Overview

This document provides comprehensive information about Broadcom's Thor family of high-performance Ethernet Network Interface Cards (NICs), including technical specifications, form factors, signaling technologies, and compatible optics/DAC cables.

## Document Version
- **Last Updated:** 2025-11-06
- **Scope:** Thor (BCM57508), Thor2 (BCM57608), Thor Ultra (BCM57708)

---

## Table of Contents

1. [Thor Series Overview](#thor-series-overview)
2. [Thor Generation 1 (BCM57508)](#thor-generation-1-bcm57508)
3. [Thor2 Generation (BCM57608)](#thor2-generation-bcm57608)
4. [Thor Ultra Generation (BCM57708)](#thor-ultra-generation-bcm57708)
5. [Form Factors and Connectors](#form-factors-and-connectors)
6. [Signaling Technologies](#signaling-technologies)
7. [Supported Cables and Optics](#supported-cables-and-optics)
8. [Third-Party Compatible Optics](#third-party-compatible-optics)
9. [Compatibility Matrix](#compatibility-matrix)

---

## Thor Series Overview

The Broadcom Thor family represents Broadcom's high-performance Ethernet NIC portfolio designed for data center, cloud, AI/ML, and high-performance computing applications. The series emphasizes:

- **High Throughput:** From 100G to 800G aggregate bandwidth
- **Advanced RDMA:** Hardware-based RoCEv2 with congestion control
- **Security:** Silicon Root-of-Trust (RoT), secure boot, attestation
- **TruFlow Technology:** Hardware offload engine for flow processing
- **AI Optimization:** Ultra Ethernet Consortium (UEC) compliance for AI workloads

### Key Technologies

- **RoCEv2:** RDMA over Converged Ethernet with hardware congestion control
- **TruFlow:** Hardware acceleration engine for flow offload and Open vSwitch
- **Silicon RoT:** Hardware-based root of trust for secure boot
- **Attestation:** Firmware integrity verification
- **TLS/QUIC Offload:** Inline encryption/decryption for secure communications
- **SR-IOV:** Single Root I/O Virtualization with up to 1,024 VFs

### Thor Naming Convention

Broadcom uses the following naming scheme:
- **BCM57508:** Thor (Generation 1) - 200G controller
- **BCM57608:** Thor2 (Generation 2) - 400G controller
- **BCM57708:** Thor Ultra (Generation 3) - 800G controller

### Market Positioning

The Thor family competes directly with:
- NVIDIA ConnectX series
- Intel E810/E910 series
- Marvell OCTEON family

---

## Thor Generation 1 (BCM57508)

### Overview
The first-generation Thor introduced 200Gb/s Ethernet with 50G PAM-4 SerDes technology and PCIe Gen 4.0 support.

### Controller Specifications

**BCM57508 Controller:**
- **Technology:** 200GbE MAC controller with integrated dual-channel 100GbE SFI transceiver
- **SerDes:** 50G PAM-4 and 25G NRZ signaling
- **PCIe:** Gen 4.0 x16 host interface
- **Max Bandwidth:** 200Gb/s aggregate

### Adapter Models

#### P2100G - Dual-Port 100G PCIe NIC

**Part Number:** BCM957508-P2100G

**Specifications:**
- **Form Factor:** Standard PCIe add-in card (CEM)
- **PCIe Interface:** Gen 4.0 x16
- **Ports:** 2x QSFP56 connectors
- **Speeds:** Dual 2x100/50/25/10GbE or Single 1x200/100/50/25/10GbE
- **SerDes:** 4x50G PAM-4 per port (or 4x25G NRZ backward compatible)
- **Power Consumption:** 16.0W typical with passive DAC at 55°C ambient
- **Dimensions:** 167.64mm (W) x 68.91mm (H)
- **Virtualization:** SR-IOV with up to 1,024 VFs

**Key Features:**
- TruFlow hardware acceleration for OvS offload
- RoCEv2 with hardware congestion control
- Silicon Root-of-Trust and attestation
- Secure boot with signed firmware
- TLS inline encryption/decryption

#### N2100G - Dual-Port 100G OCP 3.0 NIC

**Part Number:** BCM957508-N2100G

**Specifications:**
- **Form Factor:** OCP 3.0 Small Form Factor (SFF)
- **PCIe Interface:** Gen 4.0 x16
- **Ports:** 2x QSFP56 connectors
- **Speeds:** Dual 2x100/50/25/10GbE or Single 1x200/100/50/25/10GbE
- **SerDes:** 4x50G PAM-4 per port

**Differences from P2100G:**
- OCP 3.0 form factor instead of standard PCIe
- Designed for cloud/hyperscale deployments
- Same controller and features as P2100G

#### P1200G - Single-Port 200G PCIe NIC

**Part Number:** BCM957508-P1200G

**Specifications:**
- **Form Factor:** Standard PCIe add-in card (CEM)
- **PCIe Interface:** Gen 4.0 x16
- **Ports:** 1x QSFP56 connector
- **Speeds:** 1x200/100/50/40/25/10GbE
- **SerDes:** 4x50G PAM-4

**Use Cases:**
- Single high-bandwidth connection
- Storage acceleration
- High-throughput database servers

#### N1200G - Single-Port 200G OCP 3.0 NIC

**Part Number:** BCM957508-N1200G

**Specifications:**
- **Form Factor:** OCP 3.0 SFF
- **PCIe Interface:** Gen 4.0 x16
- **Ports:** 1x QSFP56 connector
- **Speeds:** 1x200/100/50/40/25/10GbE
- **SerDes:** 4x50G PAM-4 with short-haul (SH) optimization

#### P2200G - Dual-Port 200G PCIe NIC (BCM57508 variant)

**Part Number:** BCM957508-P2200G

**Specifications:**
- **Form Factor:** Standard PCIe add-in card (CEM)
- **PCIe Interface:** Gen 4.0 x16
- **Ports:** 2x QSFP56 connectors
- **Speeds:** Dual 2x200GbE (using 50G PAM-4 on each port)
- **SerDes:** 4x50G PAM-4 per port

**Important Note:**
This is the BCM57508-based P2200G. There is also a BCM57608-based P2200G (Thor2) with different capabilities. See Thor2 section below.

### Technical Specifications Table

| Feature | P2100G | N2100G | P1200G | N1200G | P2200G |
|---------|--------|--------|--------|--------|--------|
| Controller | BCM57508 | BCM57508 | BCM57508 | BCM57508 | BCM57508 |
| Form Factor | PCIe CEM | OCP 3.0 | PCIe CEM | OCP 3.0 | PCIe CEM |
| PCIe Gen | 4.0 x16 | 4.0 x16 | 4.0 x16 | 4.0 x16 | 4.0 x16 |
| Ports | 2x QSFP56 | 2x QSFP56 | 1x QSFP56 | 1x QSFP56 | 2x QSFP56 |
| Max Speed | 2x100G or 1x200G | 2x100G or 1x200G | 1x200G | 1x200G | 2x200G |
| SerDes | 50G PAM-4 | 50G PAM-4 | 50G PAM-4 | 50G PAM-4 | 50G PAM-4 |
| Power (Typical) | 16W | ~16W | ~14W | ~14W | ~18W |

### 200G Configuration Note

**Important:** By default, the BCM957508 network adapter is configured as a 2-port device supporting up to 100G on each port. To use 200G speed:
1. The device must be reconfigured as a 1-port device
2. The 200G link speed must be explicitly enabled
3. Configuration is done through Broadcom's management tools

---

## Thor2 Generation (BCM57608)

### Overview
Thor2 represents the second generation with 400Gb/s aggregate bandwidth, PCIe Gen 5.0, and 100G PAM-4 SerDes technology.

### Controller Specifications

**BCM57608 Controller:**
- **Technology:** 400GbE MAC controller with 100G PAM-4 SerDes
- **SerDes:** 100G PAM-4 (QSFP112), 50G PAM-4 (backward compatible)
- **PCIe:** Gen 5.0 x16 host interface
- **Max Bandwidth:** 400Gb/s aggregate

### Adapter Models

#### P2200G - Dual-Port 200G PCIe NIC (Thor2)

**Part Number:** BCM957608-P2200GQF00

**Specifications:**
- **Form Factor:** Standard PCIe add-in card (CEM), low profile compatible
- **PCIe Interface:** Gen 5.0 x16
- **Ports:** 2x QSFP112 connectors
- **Speeds:** Dual 2x200/100/50/25GbE or Single 1x400/200/100/50/25GbE
- **SerDes:** 4x100G PAM-4 per port (or 4x50G PAM-4 backward compatible)
- **Max Bandwidth:** 400Gb/s aggregate

**Key Features:**
- TruFlow 400G hardware acceleration
- RoCEv2 with DCN (Data Center Network) and SARA (Scalable Accurate Resource Allocation)
- TLS/QUIC inline encryption offload
- Transmit pacing for congestion management
- Secure boot and attestation
- Silicon Root-of-Trust
- Peer Memory Direct support

#### N2200G - Dual-Port 200G OCP 3.0 NIC (Thor2)

**Part Number:** BCM957608-N2200G

**Specifications:**
- **Form Factor:** OCP 3.0
- **PCIe Interface:** Gen 5.0 x16
- **Ports:** 2x QSFP112 connectors
- **Speeds:** Dual 2x200/100/50/25GbE or Single 1x400/200/100/50/25GbE
- **SerDes:** 4x100G PAM-4 per port

#### P1400G - Single-Port 400G PCIe NIC

**Part Number:** BCM957608-P1400GDF00

**Specifications:**
- **Form Factor:** Standard PCIe add-in card (CEM), low profile compatible
- **PCIe Interface:** Gen 5.0 x16
- **Ports:** 1x QSFP112-DD connector
- **Speeds:** 1x400/200/100/50/25GbE
- **SerDes:** 4x100G PAM-4 (8 lanes available in QSFP112-DD)

**Notes:**
- Uses QSFP112-DD connector (not standard QSFP112)
- Single-port configuration for maximum per-port bandwidth
- Ideal for AI/ML and high-performance storage

#### N1400G - Single-Port 400G OCP 3.0 NIC

**Part Number:** BCM957608-N1400GDP00

**Specifications:**
- **Form Factor:** OCP 3.0
- **PCIe Interface:** Gen 5.0 x16
- **Ports:** 1x QSFP112-DD connector
- **Speeds:** 1x400/200/100/50/25GbE
- **SerDes:** 4x100G PAM-4

### Technical Specifications Table

| Feature | P2200G | N2200G | P1400G | N1400G |
|---------|--------|--------|--------|--------|
| Controller | BCM57608 | BCM57608 | BCM57608 | BCM57608 |
| Form Factor | PCIe CEM | OCP 3.0 | PCIe CEM | OCP 3.0 |
| PCIe Gen | 5.0 x16 | 5.0 x16 | 5.0 x16 | 5.0 x16 |
| Ports | 2x QSFP112 | 2x QSFP112 | 1x QSFP112-DD | 1x QSFP112-DD |
| Max Speed | 2x200G or 1x400G | 2x200G or 1x400G | 1x400G | 1x400G |
| SerDes | 100G PAM-4 | 100G PAM-4 | 100G PAM-4 | 100G PAM-4 |
| Connector Type | QSFP112 | QSFP112 | QSFP112-DD | QSFP112-DD |

### Thor2 Advanced Features

#### TruFlow Technology
- **Description:** Hardware-based flow offload engine
- **Capabilities:**
  - Open vSwitch (OvS) offload
  - 400G flow processing at line rate
  - Stateful flow tracking
  - Connection tracking offload
- **Benefits:** Frees CPU resources for application workloads

#### RoCEv2 Enhancements
- **DCN:** Data Center Network congestion control
- **SARA:** Scalable Accurate Resource Allocation
- **Hardware Congestion Management:** PFC, ECN support
- **Low Latency:** Sub-microsecond RDMA latency

#### Security Features
- **Silicon Root-of-Trust:** Hardware security anchor
- **Secure Boot:** Verified firmware loading
- **Attestation:** Runtime firmware integrity checking
- **TLS/QUIC Offload:** Line-rate encryption/decryption
- **MACsec:** Layer 2 encryption (optional)

#### AI/ML Optimizations
- **Transmit Pacing:** Precise packet timing for AI workloads
- **Peer Memory Direct:** GPU Direct RDMA support
- **Adaptive Routing:** Multi-path load balancing
- **Congestion Control:** UEC-ready features

---

## Thor Ultra Generation (BCM57708)

### Overview
Thor Ultra is Broadcom's third-generation 800G AI Ethernet NIC, announced in October 2025 and designed specifically for large-scale AI cluster deployments.

### Controller Specifications

**BCM57708 Controller:**
- **Technology:** 800GbE AI Ethernet controller
- **SerDes:** 200G PAM-4 (4 lanes) or 100G PAM-4 (8 lanes)
- **PCIe:** Gen 6.0 x16 host interface
- **Max Bandwidth:** 800Gb/s

### Key Innovations

#### Ultra Ethernet Consortium (UEC) Compliance
Thor Ultra is **fully feature-compliant** with the UEC specification, making it the industry's first UEC-certified 800G NIC.

**UEC Features:**
- **Packet-level Multipathing:** Efficient load balancing across multiple paths
- **Out-of-Order Delivery:** Direct packet delivery to XPU memory without reordering overhead
- **Selective Retransmission:** Only retransmit lost packets, not entire windows
- **Programmable Congestion Control:** Algorithm customization for AI workloads

#### SerDes Technology

**200G PAM-4 Configuration:**
- 4 lanes @ 200G PAM-4 = 800Gb/s
- Long-reach passive copper support (>2m at 112G rates)
- Industry's lowest Bit Error Rate (BER)
- Reduced link flaps and improved Job Completion Time (JCT)

**100G PAM-4 Configuration:**
- 8 lanes @ 100G PAM-4 = 800Gb/s
- Alternative configuration for different reach/power requirements

#### Scale and Performance

**Massive Scale Support:**
- Capable of interconnecting **100,000+ XPUs** (GPUs, TPUs, custom accelerators)
- Designed for trillion-parameter AI model training
- Hyperscale deployment optimized

**Performance Metrics:**
- 800Gb/s line-rate throughput
- Sub-microsecond latency for RDMA
- Line-rate encryption/decryption via PSP offload

### Adapter Models

**Note:** As of November 2025, Thor Ultra is in sampling phase. Specific adapter part numbers have not been publicly released.

**Expected Form Factors:**
- Standard PCIe CEM (add-in card)
- OCP 3.0 (cloud/hyperscale deployments)

**Expected Connector:**
- Single 800G port with OSFP112 connector (using 112G PAM-4 signaling)
- Alternative: OSFP-DD or custom high-density connector

### Technical Specifications

| Feature | Thor Ultra (Projected) |
|---------|------------------------|
| Controller | BCM57708 |
| Form Factor | PCIe CEM, OCP 3.0 |
| PCIe Gen | 6.0 x16 |
| Ports | 1x 800G (expected) |
| Max Speed | 800Gb/s |
| SerDes | 200G PAM-4 (4 lanes) or 100G PAM-4 (8 lanes) |
| Power | ~50W (approx.) |
| Availability | Sampling now, production 2026 |

### Advanced Features

#### Security
- **Line-rate Encryption:** PSP (Platform Security Processor) offload for TLS/QUIC
- **Secure Boot:** Signed firmware with cryptographic verification
- **Device Attestation:** Runtime integrity checking
- **Silicon RoT:** Hardware-based trust anchor

#### UEC-Specific Capabilities
- **Programmable Congestion Control Pipeline:** Customizable algorithms
- **Packet-level Multipathing:** Load balancing at packet granularity
- **Out-of-Order Packet Delivery:** Direct XPU memory delivery
- **Selective Retransmission:** Efficient error recovery

#### AI Optimizations
- **GPU Direct RDMA:** Zero-copy GPU-to-GPU communication
- **Precision Timing:** Packet pacing for synchronous training
- **Adaptive Load Balancing:** Dynamic path selection
- **Low-Latency RDMA:** Hardware-accelerated RDMA operations

### Availability

- **Current Status:** Sampling (as of October 2025)
- **Expected Production:** 2026 through Broadcom OEM partners
- **Target Market:** AI factories, hyperscale data centers, HPC

---

## Form Factors and Connectors

### PCIe Form Factors

#### Standard PCIe CEM (Add-in Card)
- **Description:** Traditional PCIe expansion card
- **Bracket Types:** Standard-height and low-profile (some models)
- **Use Cases:** General server deployments, workstations
- **Models:** P-series (P2100G, P2200G, P1400G, etc.)

**Dimensions (Typical):**
- Width: 167.64mm
- Height: 68.91mm (standard), 64.41mm (low profile)

#### OCP 3.0 (Open Compute Project)
- **Description:** Mezzanine-style card for cloud/hyperscale servers
- **Size:** Small Form Factor (SFF)
- **Benefits:** Space-efficient, hot-swappable, standardized
- **Use Cases:** Cloud providers, hyperscale deployments
- **Models:** N-series (N2100G, N2200G, N1400G, etc.)

### Connector Types

#### QSFP56
- **Lanes:** 4 electrical lanes
- **Lane Speed:** Up to 50G PAM-4 (56Gb/s with encoding)
- **Total Bandwidth:** 200Gb/s
- **Pin Count:** 38 pins
- **Used In:** Thor Gen 1 (BCM57508)
- **Backward Compatible:** QSFP28 (100G), QSFP+ (40G)

#### QSFP112
- **Lanes:** 4 electrical lanes (8 optical lanes possible)
- **Lane Speed:** Up to 100G PAM-4 (112Gb/s with encoding)
- **Total Bandwidth:** 400Gb/s
- **Pin Count:** 38 pins
- **Used In:** Thor2 (BCM57608)
- **Backward Compatible:** QSFP56 (200G), QSFP28 (100G)

#### QSFP112-DD (Double Density)
- **Lanes:** 8 electrical lanes
- **Lane Speed:** Up to 100G PAM-4
- **Total Bandwidth:** 400Gb/s (can utilize up to 8 lanes)
- **Pin Count:** 76 pins (2x 38-pin rows)
- **Used In:** Thor2 single-port models (P1400G, N1400G)
- **Note:** Provides flexibility for breakout configurations

#### OSFP (Projected for Thor Ultra)
- **Lanes:** 8 electrical lanes
- **Lane Speed:** Up to 100G or 200G PAM-4
- **Total Bandwidth:** 800Gb/s
- **Pin Count:** 74 pins
- **Expected Use:** Thor Ultra (BCM57708)

**Variant: OSFP112**
- Uses 112G PAM-4 signaling (4 lanes @ 200G = 800G)
- Likely connector type for Thor Ultra

### Connector Compatibility Summary

| Connector | Thor Gen 1 | Thor2 | Thor Ultra |
|-----------|------------|-------|------------|
| QSFP56 | Native | Backward Compat | No |
| QSFP28 | Backward Compat | Backward Compat | No |
| QSFP+ | Backward Compat | Backward Compat | No |
| QSFP112 | No | Native | No |
| QSFP112-DD | No | Native (single-port) | No |
| OSFP112 | No | No | Expected |

---

## Signaling Technologies

### NRZ (Non-Return-to-Zero)

**Description:** Two-level signaling (high/low voltage) representing binary 1 and 0.

**Characteristics:**
- **Bits per Symbol:** 1 bit
- **Voltage Levels:** 2
- **Speed Range:** Up to 28Gb/s per lane (25G data + encoding)

**Broadcom Thor Usage:**
- **10G NRZ:** 10GbE backward compatibility
- **25G NRZ:** 25GbE (QSFP28 backward compatibility)

**Supported In:**
- Thor Gen 1 (BCM57508): Backward compatibility mode
- Thor2 (BCM57608): Backward compatibility mode

### PAM4 (Pulse Amplitude Modulation 4-Level)

**Description:** Four-level signaling encoding 2 bits per symbol using four distinct voltage levels.

**Characteristics:**
- **Bits per Symbol:** 2 bits
- **Voltage Levels:** 4
- **Efficiency:** Doubles data rate vs. NRZ at same baud rate

#### 50G PAM-4 (56Gb/s with encoding)

**Specifications:**
- **Data Rate:** 50Gb/s per lane
- **Baud Rate:** ~51.5625 GBd (often referred to as 56G)
- **Total Bandwidth:** 200Gb/s (4 lanes)
- **Encoding:** 64b/66b (~3.125% overhead)

**Broadcom Thor Usage:**
- **Thor Gen 1 (BCM57508):** Native SerDes technology
- **200GbE:** 4 lanes @ 50G PAM-4
- **100GbE:** 2 lanes @ 50G PAM-4 or 4 lanes @ 25G NRZ

**Form Factor:** QSFP56

#### 100G PAM-4 (112Gb/s with encoding)

**Specifications:**
- **Data Rate:** 100Gb/s per lane
- **Baud Rate:** ~103.125 GBd (often referred to as 112G)
- **Total Bandwidth:** 400Gb/s (4 lanes) or 800Gb/s (8 lanes)
- **Encoding:** 64b/66b (~3.125% overhead)

**Broadcom Thor Usage:**
- **Thor2 (BCM57608):** Native SerDes technology
- **400GbE:** 4 lanes @ 100G PAM-4
- **200GbE:** 2 lanes @ 100G PAM-4 or 4 lanes @ 50G PAM-4

**Form Factor:** QSFP112, QSFP112-DD

#### 200G PAM-4 (224Gb/s with encoding - Projected)

**Specifications:**
- **Data Rate:** 200Gb/s per lane
- **Baud Rate:** ~206.25 GBd (often referred to as 224G)
- **Total Bandwidth:** 800Gb/s (4 lanes) or 1.6Tb/s (8 lanes)
- **Encoding:** 64b/66b (~3.125% overhead)

**Broadcom Thor Usage:**
- **Thor Ultra (BCM57708):** Expected native SerDes
- **800GbE:** 4 lanes @ 200G PAM-4

**Form Factor:** OSFP112 (projected)

### Signaling Technology Comparison

| Technology | Bits/Symbol | Lane Speed | 4-Lane BW | 8-Lane BW | Thor Generation |
|------------|-------------|------------|-----------|-----------|-----------------|
| 10G NRZ | 1 | 10Gb/s | 40Gb/s | 80Gb/s | All (backward) |
| 25G NRZ | 1 | 25Gb/s | 100Gb/s | 200Gb/s | All (backward) |
| 50G PAM-4 | 2 | 50Gb/s | 200Gb/s | 400Gb/s | Thor, Thor2 |
| 100G PAM-4 | 2 | 100Gb/s | 400Gb/s | 800Gb/s | Thor2, Thor Ultra |
| 200G PAM-4 | 2 | 200Gb/s | 800Gb/s | 1.6Tb/s | Thor Ultra |

---

## Supported Cables and Optics

### Broadcom Cable Compatibility Philosophy

From official Broadcom documentation:

> "Broadcom Ethernet adapters are generally expected to work with any IEEE-compliant DAC, AOC, or Optical Transceivers, even if a particular interconnect might not have been part of a qualification cycle within Broadcom's interoperability lab."

**Key Points:**
- IEEE compliance is the primary requirement
- Broadcom tests a subset of cables but supports broader compatibility
- Interoperability testing does not include full BER, power, or temperature testing
- Official Interconnect Compatibility Lists (ICLs) are available on Broadcom TechDocs

### Cable Selection Process

1. **Determine SerDes Speed:**
   - 56G (50G PAM-4) for Thor Gen 1
   - 112G (100G PAM-4) for Thor2
   - 224G (200G PAM-4) for Thor Ultra (projected)

2. **Select Connector Type:**
   - QSFP56 for 100G/200G (Thor Gen 1)
   - QSFP112 or QSFP112-DD for 200G/400G (Thor2)
   - OSFP112 for 800G (Thor Ultra - projected)

3. **Choose Cable Type Based on Distance:**
   - 0.5-3m: Passive DAC
   - 3-5m: Passive DAC (high-quality) or Active DAC
   - 5-10m: Active Electrical Cable (AEC) or Active Copper Cable (ACC)
   - 10-100m: Active Optical Cable (AOC)
   - 100m+: Optical transceivers

### Thor Gen 1 (BCM57508) Cables

#### QSFP56 200G Cables

**Direct Attach Copper (DAC) - Passive:**
- **Lengths:** 0.5m, 1m, 2m, 3m
- **Connector:** QSFP56 to QSFP56
- **Power:** Passive (no electronics)
- **Use Case:** Short-reach, intra-rack connections

**Direct Attach Copper (DAC) - Active:**
- **Lengths:** 3m, 5m, 7m
- **Connector:** QSFP56 to QSFP56
- **Power:** Active signal conditioning
- **Use Case:** Extended copper reach

**Active Optical Cable (AOC):**
- **Lengths:** 5m, 10m, 20m, 30m, 50m, 100m
- **Connector:** QSFP56 to QSFP56 with integrated optics
- **Power:** Active (requires power from port)
- **Use Case:** Cross-rack, flexible installations

**Breakout Cables:**
- **QSFP56 to 2x QSFP28:** 200G to 2x100G
- **QSFP56 to 4x SFP28:** 200G to 4x50G (if supported)

#### QSFP28 100G Cables (Backward Compatible)

**Direct Attach Copper (DAC):**
- **Lengths:** 0.5m, 1m, 2m, 3m, 5m
- **Connector:** QSFP28 to QSFP28
- **Speeds:** 100G, 40G

**Active Optical Cable (AOC):**
- **Lengths:** 5m to 100m
- **Connector:** QSFP28 to QSFP28

**Breakout Cables:**
- **QSFP28 to 4x SFP28:** 100G to 4x25G

#### Optical Transceivers for Thor Gen 1

**QSFP56 200G Transceivers:**
- **200G SR4:** 850nm VCSEL, OM4 100m, 4x50G PAM-4, MPO-12 connector
- **200G DR4:** 1310nm, SMF 500m, 4x50G PAM-4, MPO-12 connector
- **200G FR4:** 1310nm CWDM, SMF 2km, 4x50G PAM-4, LC duplex
- **200G LR4:** LAN-WDM, SMF 10km, 4x50G PAM-4, LC duplex

**QSFP28 100G Transceivers (Backward Compatible):**
- **100G SR4:** 850nm, OM4 100m, 4x25G NRZ, MPO-12
- **100G LR4:** 1310nm LAN-WDM, SMF 10km, LC duplex
- **100G DR1:** 1310nm, SMF 500m, 1x100G PAM-4, LC duplex

### Thor2 (BCM57608) Cables

#### QSFP112 400G Cables

**Direct Attach Copper (DAC) - Passive:**
- **Lengths:** 0.5m, 1m, 2m, 3m (Broadcom actively qualifying >2m DACs for 112G)
- **Connector:** QSFP112 to QSFP112
- **Power:** Passive
- **Use Case:** Short-reach, high-density deployments

**Direct Attach Copper (DAC) - Active:**
- **Lengths:** 3m, 5m
- **Connector:** QSFP112 to QSFP112
- **Power:** Active signal conditioning
- **Use Case:** Extended reach within rack

**Active Optical Cable (AOC):**
- **Lengths:** 5m, 10m, 20m, 30m, 50m, 100m
- **Connector:** QSFP112 to QSFP112 with integrated optics
- **Power:** Active
- **Use Case:** Cross-rack, flexible routing

**Breakout Cables:**
- **QSFP112 to 2x QSFP56:** 400G to 2x200G
- **QSFP112 to 4x QSFP28:** 400G to 4x100G
- **QSFP112 to 8x SFP28:** 400G to 8x50G (some configurations)

#### QSFP112-DD 400G Cables (P1400G/N1400G)

**Direct Attach Copper (DAC):**
- **Lengths:** 0.5m, 1m, 2m, 3m
- **Connector:** QSFP112-DD to QSFP112-DD
- **Note:** Can also use QSFP112-DD to OSFP adapters/cables

**Breakout Cables:**
- **QSFP112-DD to 2x QSFP112:** Split to 2x200G
- **QSFP112-DD to 4x QSFP56:** Split to 4x100G

#### QSFP56 200G Cables (Backward Compatible)

Same as Thor Gen 1 - all QSFP56 cables supported.

#### QSFP28 100G Cables (Backward Compatible)

Same as Thor Gen 1 - all QSFP28 cables supported.

#### Optical Transceivers for Thor2

**QSFP112 400G Transceivers:**
- **400G SR8:** 850nm VCSEL, OM4 100m, 8x50G PAM-4, 2x MPO-12 or MPO-16 connector
- **400G SR4.2:** 850nm VCSEL, OM4 100m, 4x100G PAM-4, MPO-12 connector
- **400G DR4:** 1310nm, SMF 500m, 4x100G PAM-4, MPO-12 connector
- **400G FR4:** 1310nm CWDM, SMF 2km, 4x100G PAM-4, LC duplex
- **400G LR4:** LAN-WDM, SMF 10km, 4x100G PAM-4, LC duplex
- **400G ER8:** 1310nm, SMF 40km, 8x50G PAM-4 (long-haul)

**QSFP112-DD 400G Transceivers:**
- Supports same transceivers as QSFP112
- Can use QSFP112-DD native modules with additional capabilities

**Backward Compatible Transceivers:**
- All QSFP56 200G transceivers
- All QSFP28 100G transceivers

### Thor Ultra (BCM57708) Cables (Projected)

**Note:** Thor Ultra is currently sampling. Cable specifications are projected based on announced SerDes capabilities.

#### OSFP 800G Cables (Expected)

**Direct Attach Copper (DAC) - Passive:**
- **Lengths:** 0.5m, 1m, 1.5m, 2m
- **Connector:** OSFP to OSFP
- **Technology:** 4x200G PAM-4 or 8x100G PAM-4
- **Note:** Broadcom mentioned long-reach passive copper support

**Direct Attach Copper (DAC) - Active:**
- **Lengths:** 2m, 3m, 5m
- **Connector:** OSFP to OSFP
- **Technology:** Active Electrical Cable (AEC)

**Active Optical Cable (AOC):**
- **Lengths:** 10m, 20m, 30m, 50m, 100m
- **Connector:** OSFP to OSFP with integrated optics

**Breakout Cables (Expected):**
- **OSFP to 2x QSFP112:** 800G to 2x400G
- **OSFP to 4x QSFP56:** 800G to 4x200G
- **OSFP to 8x QSFP28:** 800G to 8x100G

#### OSFP 800G Optical Transceivers (Projected)

**Expected 800G Transceivers:**
- **800G SR8:** 850nm, OM4 50-100m, 8x100G PAM-4, 2x MPO-12
- **800G DR4:** 1310nm, SMF 500m, 4x200G PAM-4, MPO-12
- **800G DR8:** 1310nm, SMF 500m, 8x100G PAM-4, 2x MPO-12
- **800G FR4:** 1310nm CWDM, SMF 2km, 4x200G PAM-4, LC duplex
- **800G LR4:** LAN-WDM, SMF 10km, 4x200G PAM-4, LC duplex

### Cable Type Selection Guide

| Distance | Recommended Cable | Pros | Cons |
|----------|-------------------|------|------|
| 0.5-2m | Passive DAC | Lowest cost, low latency, no power | Bulky, rigid |
| 2-3m | Passive DAC (high-quality) | Low cost, no power | Limited reach, rigid |
| 3-5m | Active DAC or AEC | Better signal integrity | Requires power, higher cost |
| 5-10m | Active Copper Cable (ACC) | Longer copper reach | Higher cost, power consumption |
| 10-100m | Active Optical Cable (AOC) | Lightweight, flexible, EMI immune | Not field-serviceable |
| 100m-500m | SR/DR Optical Transceiver + Fiber | Field-replaceable, proven | Two components, higher cost |
| 500m-10km | FR/LR Optical Transceiver + Fiber | Long reach | Expensive |

---

## Third-Party Compatible Optics

### Manufacturer Ecosystem

Major transceiver manufacturers supply components to both OEM and third-party vendors:
- **Component Suppliers:** Avago, Finisar (II-VI), Lumentum, Inphi, Credo
- **Third-Party Vendors:** FS.com, NADDOD, Fiberstore, ProLabs, 10Gtek, Approved Networks

### Third-Party Testing and Validation

#### FS.com
- **Compatibility:** Offers Broadcom-compatible cables and transceivers
- **Testing:** Tests products on various platforms before shipment
- **Product Range:** DAC, AOC, SR/LR transceivers for 100G, 200G, 400G
- **Warranty:** Typically 3-5 year warranty

**Example Products:**
- Broadcom BCM957508-P2100G compatible: QSFP56 100G DAC, AOC
- Broadcom BCM957608-P2200G compatible: QSFP112 200G DAC, transceivers
- Broadcom BCM957608-P1400G compatible: QSFP112-DD 400G cables

#### NADDOD
- **Focus:** High-speed Ethernet and AI networking
- **Compatibility:** Broadcom-compatible product line
- **Testing:** Validated on Broadcom platforms
- **Specialization:** 400G/800G products

#### Approved Networks
- **Product Range:** AEC cables, breakout cables
- **Standards Compliance:** CMIS 3.0/4.0 compliant
- **Notable Products:**
  - 400G QSFP-DD AEC to 4x QSFP28 breakout (CMIS 3.0)
  - 400G OSFP AEC to 4x QSFP28 breakout (CMIS 3.0)

### Broadcom's Position on Third-Party Optics

From official documentation:

> "Broadcom Ethernet adapters are generally expected to work with any IEEE-compliant DAC, AOC, or Optical Transceivers."

**Key Points:**
- IEEE compliance is required
- Broadcom does not officially certify third-party modules
- Warranty on NIC hardware is not voided by third-party optics
- For support cases, Broadcom may request testing with known-good cables

### Compatibility Considerations

#### What to Check:
1. **IEEE Compliance:** Ensure transceiver meets IEEE 802.3 standards
2. **Form Factor Match:** QSFP56, QSFP112, etc.
3. **Speed Support:** NRZ vs. PAM-4, correct lane speeds
4. **Connector Type:** MPO-12, LC duplex, etc.
5. **Reach Requirements:** SR (short), DR (data rate), LR (long)
6. **Power Budget:** Ensure server/switch can provide required power
7. **CMIS Compliance:** CMIS 4.0+ recommended for 400G

#### Testing Recommendations:
1. **Pilot Testing:** Test small quantities before bulk purchase
2. **Link Quality Monitoring:** Use Broadcom tools to check BER
3. **Performance Validation:** Run throughput and latency tests
4. **Environmental Testing:** Verify operation at expected temperatures
5. **Interoperability:** Test with actual switches/NICs in deployment

### Cost Comparison

Third-party optics typically offer **40-70% cost savings:**

| Product Type | OEM Cost (Est.) | Third-Party (Est.) | Savings |
|--------------|-----------------|-------------------|---------|
| QSFP28 100G SR4 | $300-500 | $100-200 | 50-67% |
| QSFP56 200G SR4 | $800-1200 | $250-450 | 60-70% |
| QSFP112 400G SR8 | $1500-2500 | $500-1000 | 60-67% |
| QSFP112 400G DR4 | $2000-3000 | $700-1200 | 60-65% |
| QSFP28 100G DAC 3m | $100-150 | $40-70 | 50-60% |
| QSFP112 400G DAC 2m | $250-400 | $100-180 | 50-60% |

*Prices are approximate and vary by volume and vendor.*

### Warranty and Support

**NIC Warranty:**
- Installing third-party optics does **NOT** void Broadcom NIC warranty
- NIC hardware warranty remains valid
- Industry standard across NIC manufacturers

**Optic Warranty:**
- Third-party vendors typically offer 3-5 year warranties on transceivers
- Some offer lifetime warranties on passive DAC cables
- RMA processes vary by vendor

**Support Considerations:**
- Broadcom support may request testing with known-good cables for troubleshooting
- Keep a small stock of Broadcom-tested cables for diagnostics
- Document third-party optic testing and validation

---

## Compatibility Matrix

### Thor Gen 1 (BCM57508) Compatibility

| Adapter Model | Form Factor | Max Speed | Connector | Compatible Cables/Optics | Backward Compat |
|---------------|-------------|-----------|-----------|--------------------------|-----------------|
| **P2100G** | PCIe CEM | 2x100G or 1x200G | 2x QSFP56 | QSFP56 200G DAC/AOC/SR4/DR4<br>QSFP28 100G (all types) | QSFP28, QSFP+ |
| **N2100G** | OCP 3.0 | 2x100G or 1x200G | 2x QSFP56 | Same as P2100G | QSFP28, QSFP+ |
| **P1200G** | PCIe CEM | 1x200G | 1x QSFP56 | QSFP56 200G DAC/AOC/SR4/DR4 | QSFP28, QSFP+ |
| **N1200G** | OCP 3.0 | 1x200G | 1x QSFP56 | Same as P1200G | QSFP28, QSFP+ |
| **P2200G-508** | PCIe CEM | 2x200G | 2x QSFP56 | QSFP56 200G DAC/AOC/SR4/DR4 | QSFP28, QSFP+ |

### Thor2 (BCM57608) Compatibility

| Adapter Model | Form Factor | Max Speed | Connector | Compatible Cables/Optics | Backward Compat |
|---------------|-------------|-----------|-----------|--------------------------|-----------------|
| **P2200G** | PCIe CEM | 2x200G or 1x400G | 2x QSFP112 | QSFP112 400G DAC/AOC/SR8/DR4/FR4/LR4 | QSFP56, QSFP28 |
| **N2200G** | OCP 3.0 | 2x200G or 1x400G | 2x QSFP112 | Same as P2200G | QSFP56, QSFP28 |
| **P1400G** | PCIe CEM | 1x400G | 1x QSFP112-DD | QSFP112-DD 400G DAC/AOC<br>QSFP112 400G (all types) | Limited |
| **N1400G** | OCP 3.0 | 1x400G | 1x QSFP112-DD | Same as P1400G | Limited |

### Thor Ultra (BCM57708) Compatibility (Projected)

| Adapter Model | Form Factor | Max Speed | Connector | Compatible Cables/Optics | Backward Compat |
|---------------|-------------|-----------|-----------|--------------------------|-----------------|
| **TBD** | PCIe CEM | 800G | 1x OSFP112 (expected) | OSFP 800G DAC/AEC/AOC<br>OSFP 800G SR8/DR4/FR4/LR4 | TBD |
| **TBD** | OCP 3.0 | 800G | 1x OSFP112 (expected) | Same as above | TBD |

### Port Configuration Flexibility

#### Thor Gen 1 (BCM57508)

| Configuration | Lanes | Speed per Lane | Use Case |
|---------------|-------|----------------|----------|
| 2x 100G | 4 per port | 50G PAM-4 | Dual 100GbE ports |
| 1x 200G | 4 total | 50G PAM-4 | Single 200GbE port (requires reconfiguration) |
| 2x 50G | 2 per port | 50G PAM-4 | Dual 50GbE ports |
| 2x 25G | 1 per port | 25G NRZ | Dual 25GbE ports (backward compat) |

#### Thor2 (BCM57608)

| Configuration | Lanes | Speed per Lane | Use Case |
|---------------|-------|----------------|----------|
| 1x 400G | 4 total | 100G PAM-4 | Single 400GbE port |
| 2x 200G | 4 per port | 100G PAM-4 | Dual 200GbE ports |
| 2x 100G | 2 per port | 100G PAM-4 | Dual 100GbE ports |
| 4x 100G | 1 per port | 100G PAM-4 | Breakout to 4x100GbE |
| 2x 50G | 1 per port | 50G PAM-4 | Backward compat to QSFP56 |

#### Thor Ultra (BCM57708) - Projected

| Configuration | Lanes | Speed per Lane | Use Case |
|---------------|-------|----------------|----------|
| 1x 800G | 4 lanes | 200G PAM-4 | Single 800GbE port |
| 1x 800G | 8 lanes | 100G PAM-4 | Alternative configuration |
| 2x 400G | Split | 100G PAM-4 | Breakout to 2x400GbE |

### Interoperability with Switches

| Thor NIC | Switch Port Speed | Cable/Optic Solution |
|----------|-------------------|----------------------|
| Thor 100G | 100G QSFP28 | QSFP28 100G DAC/AOC/SR4/LR4 |
| Thor 200G | 200G QSFP56 | QSFP56 200G DAC/AOC/SR4/DR4 |
| Thor 100G | 200G QSFP56 | QSFP28 100G (backward compat on switch) |
| Thor2 400G | 400G QSFP112 | QSFP112 400G DAC/AOC/SR8/DR4 |
| Thor2 200G | 200G QSFP56 | QSFP56 200G or QSFP112 (backward) |
| Thor2 400G | 2x 200G QSFP56 | QSFP112 to 2xQSFP56 splitter |
| Thor2 400G | 400G QSFP-DD | QSFP112 to QSFP-DD adapter/cable |
| Thor Ultra 800G | 800G OSFP | OSFP 800G DAC/AOC/DR4 |
| Thor Ultra 800G | 2x 400G QSFP112 | OSFP to 2xQSFP112 breakout |

---

## Appendix: Quick Reference Tables

### Speed and Form Factor Quick Reference

| Speed | Form Factor | Lane Config | Signaling | Thor Generation |
|-------|-------------|-------------|-----------|-----------------|
| 100G | QSFP28 | 4x 25G | NRZ | All (backward) |
| 100G | QSFP56 | 2x 50G | PAM-4 | Thor, Thor2 (backward) |
| 200G | QSFP56 | 4x 50G | PAM-4 | Thor, Thor2 (backward) |
| 200G | QSFP112 | 2x 100G | PAM-4 | Thor2 |
| 400G | QSFP112 | 4x 100G | PAM-4 | Thor2 |
| 400G | QSFP112-DD | 4x 100G | PAM-4 | Thor2 (single-port) |
| 800G | OSFP112 | 4x 200G | PAM-4 | Thor Ultra (projected) |

### Model Number Quick Reference

| Part Number | Marketing Name | Controller | Form Factor | Ports | Max Speed |
|-------------|----------------|------------|-------------|-------|-----------|
| BCM957508-P2100G | P2100G | BCM57508 | PCIe CEM | 2x QSFP56 | 2x100G or 1x200G |
| BCM957508-N2100G | N2100G | BCM57508 | OCP 3.0 | 2x QSFP56 | 2x100G or 1x200G |
| BCM957508-P1200G | P1200G | BCM57508 | PCIe CEM | 1x QSFP56 | 1x200G |
| BCM957508-N1200G | N1200G | BCM57508 | OCP 3.0 | 1x QSFP56 | 1x200G |
| BCM957608-P2200GQF00 | P2200G | BCM57608 | PCIe CEM | 2x QSFP112 | 2x200G or 1x400G |
| BCM957608-N2200G | N2200G | BCM57608 | OCP 3.0 | 2x QSFP112 | 2x200G or 1x400G |
| BCM957608-P1400GDF00 | P1400G | BCM57608 | PCIe CEM | 1x QSFP112-DD | 1x400G |
| BCM957608-N1400GDP00 | N1400G | BCM57608 | OCP 3.0 | 1x QSFP112-DD | 1x400G |
| BCM57708-XXXXX (TBD) | Thor Ultra | BCM57708 | PCIe CEM / OCP | 1x OSFP112 (exp) | 800G |

### Feature Comparison Across Generations

| Feature | Thor (BCM57508) | Thor2 (BCM57608) | Thor Ultra (BCM57708) |
|---------|-----------------|------------------|-----------------------|
| **Max Speed** | 200Gb/s | 400Gb/s | 800Gb/s |
| **PCIe Gen** | 4.0 x16 | 5.0 x16 | 6.0 x16 |
| **SerDes** | 50G PAM-4 | 100G PAM-4 | 200G PAM-4 (4-lane) or 100G PAM-4 (8-lane) |
| **RoCEv2** | Yes | Yes (DCN, SARA) | Yes (UEC-enhanced) |
| **TruFlow** | OvS offload | 400G offload | UEC-compliant |
| **TLS/QUIC** | Yes | Yes | Yes (PSP offload) |
| **Silicon RoT** | Yes | Yes | Yes |
| **Attestation** | Yes | Yes | Yes |
| **UEC Compliant** | No | Partial | Full |
| **Availability** | Production | Production | Sampling (2026 prod) |

### Official Documentation Resources

- **Broadcom TechDocs:** techdocs.broadcom.com
  - Cable/Interconnect Compatibility Lists
  - User Guides and Configuration Manuals
  - Release Notes and Firmware Updates

- **Broadcom Product Pages:** broadcom.com/products/ethernet-connectivity/network-adapters
  - Product specifications and datasheets
  - Selection guides and product briefs

- **Cable Compatibility:**
  - Ethernet NIC Supported Cables: docs.broadcom.com
  - BCM957608 Cable Solutions Guide: docs.broadcom.com/docs/957608-AN1XX

---

## Document Maintenance

This document should be updated as:
- Thor Ultra production specifications are finalized (expected 2026)
- New adapter models are released
- Cable compatibility lists are updated
- Third-party vendor compatibility is expanded
- Pricing and availability information changes

**Contribution:** To suggest updates or corrections, please contact the HedgeHog project maintainers.

---

## References

1. Broadcom Product Datasheets (docs.broadcom.com)
2. Broadcom TechDocs - Ethernet NIC Controllers (techdocs.broadcom.com)
3. Broadcom Cable Compatibility Documentation
4. FS.com Broadcom Ethernet Adapters Overview
5. Industry Standards: IEEE 802.3, Ultra Ethernet Consortium (UEC)
6. Silicom Thor2 Product Documentation
7. Press Releases: Thor Ultra announcement (October 2025)

---

**Document End**
