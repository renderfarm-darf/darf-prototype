# 📍 DARF Roadmap

DARF (Distributed Android Render Farm) is a native Android-first framework concept for distributed rendering using mobile devices. This roadmap outlines current development goals, planned integrations, and long-term expansions—including a future iOS sibling, DIRF.


---

## ✅ Current Status

- Public GitHub repository with documentation and early prototype scaffolding  
- Native Android render node concept (no Linux emulation or cloud reliance)  
- Renderer-agnostic architecture in place for CLI-based tools  
- Public-facing mission centered on experimentation and developer collaboration

---

## 🔧 Initial Integration Targets (PC-Side Apps)

DARF is designed to accept render jobs from desktop applications via CLI or scriptable export. Current and planned integrations include:

- **Blender** (initial proof-of-concept)
- **FFmpeg** (video transcoding, compositing)
- **After Effects** (via render queue export)
- **DaVinci Resolve** (via scriptable job export)
- **Cinema 4D / Maya** (long-term, if CLI-accessible job export is viable)

DARF is not renderer-specific—it executes jobs passed to it by a host-side dispatcher.

---

## 🔜 Near-Term Goals

- Define minimal task packet structure (input, output, render command)
- Build CLI tool or Python wrapper to generate task batches from Blender
- Android node app: accept task, validate input, execute, return result
- Host-side dispatcher to coordinate multiple Android nodes
- Basic retry logic and task caching for interrupted jobs
- Enable GitHub Discussions for community feedback

---

## 🧪 Experimental Features

- Adaptive load balancing across heterogeneous Android nodes
- Offline-first mesh coordination (no central server)
- Thermal/power-aware task scheduling
- Minimalist dashboard or CLI monitor for task status
- Encrypted asset transfer and result return

---

## 🧭 Future Expansion

### DIRF – Distributed iOS Render Farm

- Native Swift implementation based on DARF architecture
- No code porting—fresh iOS-native build encouraged
- Shared task structure and protocol logic

### PC App Integration Kits

- Tools or scripts to help users export DARF-ready jobs from supported apps
- Blender first, then generalizing to other platforms

### DARF-Control

- Optional lightweight dashboard (desktop or mobile)
- Local-first, offline-capable monitoring and control interface

---

## 🚫 Not Planned (By Design)

- Cross-platform emulation or abstraction layers
- GUI-based rendering pipelines for end users
- Cloud-based coordination or storage

---

DARF is a developer-first experiment in reclaiming mobile hardware for creative pipelines. If you're into render systems, distributed compute, or just weird ideas that might work—welcome aboard.
