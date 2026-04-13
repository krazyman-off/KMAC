# 🚀 KM-PL | KrazyMan Performance & Lag-isolation

![Version](https://img.shields.io/badge/Version-1.0.0--RELEASE-blue)
![Minecraft](https://img.shields.io/badge/Minecraft-1.21.10-green)
![License](https://img.shields.io/badge/License-Private-red)

**KM-PL** is a high-precision monitoring and optimization software suite for Minecraft servers. Unlike traditional tools, KM-PL isn't just a simple "limiter": it acts as a **lag surgeon**, capable of isolating, tracking, and throttling load sources in real-time without impacting overall server fluidity.

---

## 🛠️ Key Features

* **Pulse Tracking™**: Real-time event execution measurement down to the nanosecond.
* **GC-Free Architecture**: Engineered to minimize object allocation and eliminate Garbage Collection spikes.
* **Selective Isolation**: Selectively throttles problematic chunks or entities without affecting the rest of the world.
* **Advanced Diagnostics**: Over 40 monitoring commands (TPS, RAM, GC, Threads, Network, Hoppers, Redstone).
* **Data Export**: Fully compatible with Prometheus and JSON export for external data visualization.
* **Smart Support**: Remote diagnostic system with automated report transmission via Discord Webhooks.

---

## 📂 Core Structure

The plugin is built around **46 specialized modules**, dynamically loaded to optimize the RAM footprint:

| Category | Description |
| :--- | :--- |
| **Monitoring** | Surveillance of TPS, RAM, GC, Threads, and Network Packets. |
| **Analysis** | Memory leak detection and geographical Hotspot analyzer. |
| **Optimization** | Intelligent management of Entity AI, Hoppers, and Redstone circuits. |
| **Diagnostics** | Integrated performance benchmarking and server health dashboard. |

---

## ⌨️ Main Commands

The plugin utilizes a single root command: `/kmpl`.

* `/kmpl top`: Displays the heaviest server events (Profiler).
* `/kmpl chunks`: Identifies geographical lag zones.
* `/kmpl dashboard`: Opens the global health interface (GUI).
* `/kmpl health`: Performs a quick server health diagnostic.
* `/kmpl support`: Generates a token and sends a full report (Discord Webhooks).
* `/kmpl reload`: Performs a hot-reload of all configurations.

---

## ⚙️ Installation

1. Drop the `KM-PL.jar` file into your `plugins/` folder.
2. Restart your server.
3. Configure alert thresholds in `plugins/KM-PL/config.yml`.
4. (Optional) Set up your Discord Webhook in `settings.yml` for remote support.

---

## 🧠 Development Philosophy

KM-PL is optimized **"to the bone"**. Each module is managed via a service `Map` and a **Lazy Loading** system to ensure the plugin never consumes the performance it is meant to protect.
* **Monitor Priority**: Listeners use non-intrusive observation patterns.
* **Full Asynchronicity**: All statistics and support reports are processed off-thread.
* **Primitive Types**: Extensive use of primitives to avoid costly boxing/unboxing operations.

---

## 📞 Support & Contact

This plugin is part of the **KrazyStudio** suite. For any technical support or bug reports:
* Use the `/kmpl support` command to generate a technical dump.
* The report will automatically include your configuration and the current state of your JVM.

---
> *Powered by KrazyMan Performance & Lag-isolation - 2026*
