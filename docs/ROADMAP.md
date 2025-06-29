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
