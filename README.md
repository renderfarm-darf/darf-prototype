# DARF – Distributed Android Render Farm

DARF is a conceptual framework in active development. It invites developers to shape a native, distributed rendering system for Android from the ground up—exploring hardware-level orchestration across mobile devices, offline or in the cloud.


## ⚙️ Core Concept  
DARF is:

📱 **Android-first and native** – no Linux layers or emulators; built directly for Android hardware  
🖥️ **PC-coordinated** – render jobs are created and dispatched from desktop apps  
🛠️ **Renderer-agnostic** – supports any CLI-based renderer (e.g., Blender, FFmpeg, others)  
🔌 **Network-agnostic** – works offline over USB or LAN; no internet required

## 🚧 Current Focus

We’re beginning with integration around **Blender CLI rendering**, using Python scripts to prepare frame-based render jobs and dispatch them to Android nodes via DARF.

Key priorities:

- Define minimal task packet format (scene files, frame ranges, render commands)
- Prototype task dispatcher for Windows/macOS/Linux
- Develop lightweight Android-side agent to execute jobs and return output

## 🔭 Roadmap Highlights

See the full [ROADMAP.md](./ROADMAP.md) for details, but here's a quick glimpse:

- 👷 Task queue dispatch system (PC → Android nodes)
- 🔄 Support for batch render jobs from:
  - Blender (current)
  - FFmpeg (up next)
  - After Effects / Resolve / C4D (planned)
- 💾 Optional asset caching and job retry logic
- 📊 Basic task dashboard or command-line monitoring
- 🔐 Encrypted task transport for sensitive content
- 📱 Expansion to **DIRF** (Distributed iOS Render Farm) as a native Swift sibling project (no code porting—fresh builds only)

## 🤝 Contributing

DARF is open to thoughtful, curious developers who want to:

- Experiment with render pipelines outside the cloud
- Reclaim old hardware for creative pipelines
- Extend or adapt the task runners for specific tools

We encourage forks, discussions, and PRs. See [CONTRIBUTING.md](./verified-scenes/CONTRIBUTING.md) and join the conversation under GitHub Discussions.

## 🧪 Who It’s For

DARF isn’t for end users—not yet.

This is for **developers**, **pipeline designers**, and **creative technologists** who aren’t afraid to poke the edges of what render workflows could become.

If that’s you, welcome in.

## 📜 License

This project is licensed under the [GNU General Public License v3.0](./LICENSE).  
Use it, modify it, share it—just keep it open.

---

**Made by weird people with old phones and wild render dreams.**
