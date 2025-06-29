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
DARF is designed to accept render jobs from desktop applications via CLI or scriptable export mechanisms. Current and planned integrations include:

- **Blender** – initial proof-of-concept  
- **FFmpeg** – for transcoding, compositing, and batch video processing  
- **After Effects** – via render queue export workflows  
- **DaVinci Resolve** – through scriptable job export  
- **Cinema 4D / Maya** – long-term targets, contingent on CLI-accessible job export  

DARF is renderer-agnostic: it simply executes jobs passed to it by a host-side dispatcher.

---

## 🔜 Near-Term Goals

- Define a minimal task packet format (input paths, output targets, render commands)
- Build a CLI tool or Python wrapper to batch Blender frame jobs
- Develop Android node app to accept tasks, validate input, execute renders, and return results
- Implement host-side dispatcher to coordinate jobs across multiple Android devices
- Add basic retry logic and asset caching for incomplete or interrupted jobs
- Enable GitHub Discussions to invite feedback and community contributions
---

## 🧪 Experimental Features

- Adaptive load balancing across mixed Android hardware  
- Offline-first mesh coordination with no central server  
- Thermal- and power-aware task scheduling  
- Minimalist dashboard or CLI tool for real-time task tracking  
- Encrypted asset transfer and secure result return
---

## 🧭 Future Expansion

**DIRF – Distributed iOS Render Farm**  
- Native Swift implementation inspired by the DARF architecture  
- No code porting—clean, iOS-native builds encouraged  
- Shared task structure and communication protocol with DARF  

**PC App Integration Kits**  
- Tools and scripts to export DARF-ready jobs from supported desktop apps  
- Blender integration first, then expansion to FFmpeg, AE, Resolve, and others  

**DARF-Control**  
- Optional lightweight dashboard (desktop or mobile)  
- Local-first, offline-capable task monitoring and coordination interface
---

## 🚫 Not Planned (By Design)

- Cross-platform emulation or abstraction layers
- GUI-based rendering pipelines for end users
- Cloud-based coordination or storage

---

DARF is a developer-first experiment in reclaiming mobile hardware for creative pipelines. If you're into render systems, distributed compute, or just weird ideas that might work—welcome aboard.
