# 📍 DARF Roadmap

DARF (Distributed Android Render Farm) is a native Android-first framework concept for distributed rendering using mobile devices. This roadmap outlines current development goals, planned integrations, phased technical implementation, and long-term expansion—including a future iOS sibling, DIRF.

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

## 🚦 Phased Development Plan

DARF is staging, not sprinting. Each phase validates its part of the pipeline before handing off to the next. No guesswork. No partial builds. Just deterministic progress.

### 🔹 Phase 1 – Scene Validation & Job Packet Generation
🕒 5–7 weeks
“Parse only. Render nothing. Trust what's complete.”
- .blend-only scene ingestion
- Strict validation: camera, frame range, baked sims, compatible shaders
- Rejects invalid files silently—no patching or partials
- Outputs structured job packets, one per frame/pass
- No image generation or rendering—just clean packet prep

### 🔸 Phase 2 – Render Stub & Mesh Parser Interface
🕒 4–6 weeks
“Begin listening. Don’t draw. Confirm understanding.”
- Android (or desktop) devices receive job packets and simulate execution
- Create placeholder outputs (e.g. frame_0123_alpha.png)
- Log all inputs and track task flow through mesh simulation
- Benchmark "empty render" I/O and validate routing logic
- Phase 3 scoped during this window based on packet behavior

### 🔺 Phase 3 – Native Android Renderer (Alpha)
🕒 TBD – scoped after Phase 2 validation
“Now that I understand the jobs—let me draw one.”
- Begins with alpha or Z-depth image output (low complexity)
- Renderer receives validated packets and sandboxed job assets
- Focus on frame-specific loading, isolated rendering, and stable output

### 🧱 Phase 4 – Render Mesh Stability & Packaging
🕒 6+ weeks post-Phase 3
- Improve render output (color channels, composite passes)
- Expand support across Android versions and hardware types
- Add output packaging, retry/caching support, and asset bundling
- Begin recruiting early testers for limited release

### 🧮 Timeline Summary

| Phase   | Purpose                                 | Timeline      |
|---------|-----------------------------------------|---------------|
| Phase 1 | Scene ingestion + job packet generation | ~6 weeks      |
| Phase 2 | Simulated render + routing validation   | ~6 weeks      |
| Phase 3 | First real renders from real jobs       | ~6+ weeks     |
| Phase 4 | Output stability + test node support    | ~6 weeks      |
| Buffer  | Triage + integration & onboarding       | ~1–2 weeks    |

🎯 **Target: Week 26 – Invite a small test mesh of collaborators with stable packet routing and first-stage output.**

### 🧪 Experimental Features
- Adaptive load balancing across mixed Android hardware
- Offline-first mesh coordination with no central server
- Thermal- and power-aware task scheduling
- Minimalist dashboard or CLI tool for real-time task tracking
- Encrypted asset transfer and secure result return

### 🧭 Future Expansion
DIRF – Distributed iOS Render Farm
- Native Swift implementation inspired by the DARF architecture
- No code porting—clean, iOS-native builds encouraged
- Shared task structure and communication protocol with DARF
PC App Integration Kits
- Tools and scripts to export DARF-ready jobs from supported desktop apps
- Blender integration first, then expansion to FFmpeg, AE, Resolve, and others
DARF-Control
- Optional lightweight dashboard (desktop or mobile)
- Local-first, offline-capable task monitoring and coordination interface

🚫 Not Planned (By Design)
- Cross-platform emulation or abstraction layers
- Full-featured GUI pipelines aimed at end users
