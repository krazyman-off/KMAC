# 🚀 KM-PL | KrazyMan Performance & Lag-isolation

![Version](https://img.shields.io/badge/Version-1.1.0--STABLE-blue)
![Minecraft](https://img.shields.io/badge/Minecraft-1.21.10-green)
![Architecture](https://img.shields.io/badge/Architecture-Multi--Threaded-orange)
![GC-Status](https://img.shields.io/badge/GC--Intelligence-Active-brightgreen)

**KM-PL** is a high-precision monitoring and optimization software suite for Minecraft servers. Unlike traditional tools, KM-PL isn't just a simple "limiter": it acts as a **lag surgeon**, capable of isolating, tracking, and throttling load sources in real-time without impacting overall server fluidity.

---

## 🛠️ Key Features

* **Pulse Tracking™**: Real-time event execution measurement down to the nanosecond.
* **GC-Free Architecture**: Engineered to minimize object allocation and eliminate internal Garbage Collection spikes.
* **Cleaning Intelligence Engine**: New diagnostic engine capable of distinguishing normal load from memory leaks.
* **Selective Isolation**: Selectively throttles problematic chunks or entities without affecting the rest of the world.
* **Advanced Diagnostics**: Over 40 monitoring modules (Real TPS, RAM Velocity, GC Efficiency, Threads, Network).
* **Smart Support**: Remote diagnostic system with automated report transmission via Discord Webhooks.

---

## 🧠 Cleaning Intelligence (New v1.1)

The memory management module has been completely rebuilt to move from reactive monitoring to **predictive analysis**:

* **Memory Velocity (↑↓)**: Real-time analysis of RAM filling speed (e.g., +33 MB/s). Allows anticipating a crash 2 minutes before it happens.
* **GC Efficiency Tracking**: Calculates the "Delta" of RAM freed during each collector cycle. If efficiency is negative or too low, KM-PL identifies a memory leak.
* **GC Thrashing Detection**: Immediate alert if the server spends more than 15% of its CPU time trying to free memory unsuccessfully.
* **Dynamic Thresholds (%)**: Full migration to a percentage-based threshold system, making the plugin compatible with any RAM allocation (from 2GB to 128GB+).

---

## 📂 Core Structure

The plugin is built around **46 specialized modules**, dynamically loaded to optimize the RAM footprint:

| Category | Description |
| :--- | :--- |
| **Monitoring** | Surveillance of TPS, RAM (Velocity), GC (Efficiency), and Network. |
| **Analysis** | Memory leak detection and geographical Hotspot analyzer. |
| **Optimization** | Intelligent management of AI, Hoppers, and Redstone circuits. |
| **Diagnostics** | Integrated performance benchmarking and predictive health dashboard. |

---

## ⌨️ Main Commands

The plugin utilizes a single root command: `/kmpl`.

* `/kmpl top`: Displays the heaviest server events (Real-time profiler).
* `/kmpl memory`: Displays detailed usage, **Velocity**, and health status.
* `/kmpl gc`: Reports on Garbage Collector overhead and **Efficiency**.
* `/kmpl dashboard`: Opens the global health interface (GUI).
* `/kmpl support`: Generates a token and sends a full report to your Discord.

---

## ⚙️ Configuration

Thresholds are now managed in **percentages** for total flexibility:

```yaml
alert-system:
  # Critical threshold (Triggers the Watchdog and emergency measures)
  memory-critical-threshold-percent: 90.0
  # Warning threshold (Console and administrator notifications)
  memory-warning-threshold-percent: 80.0
```
---

## 🧠 Development Philosophy

KM-PL is optimized **"to the bone"** to ensure it never becomes a source of lag itself:

* **Full Asynchronicity**: 95% of statistical calculations are processed off-thread to ensure zero impact on TPS.
* **Primitive Types**: Extensive use of primitives (int, long, double) to avoid costly Java boxing/unboxing.
* **Lazy Loading**: Modules are only activated and loaded into memory when strictly necessary.
* **Zero-Allocation Path**: Critical monitoring loops are designed to create zero temporary objects.

---

## 📞 Support & Contact

This plugin is part of the **KrazyStudio** suite.

* Use the `/kmpl support` command for any technical requests.
* The generated report automatically includes your JVM state, active plugin list, and recent performance trends for ultra-fast diagnostics.

---
> *Powered by KrazyMan Performance & Lag-isolation - 2026*
