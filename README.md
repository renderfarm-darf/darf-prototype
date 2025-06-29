# DARF – Distributed Android Render Farm

DARF is an experimental render farm framework built entirely around **native Android devices**. It’s designed to turn recycled or dedicated Android phones and tablets into distributed render nodes—with zero reliance on cloud services or emulation layers.

This is not a finished tool—it’s a proof of concept and an open invitation for developers to explore offline, hardware-level rendering orchestration across mobile devices.

## ⚙️ Core Concept

DARF is:

- 📱 **Android-first and native** – no Linux layers, no VMs
- 🖥️ **PC-coordinated** – tasks originate from desktop apps
- 🛠️ **Renderer-agnostic** – task runners can invoke any CLI-based renderer (e.g., Blender, FFmpeg)
- 🔌 **Network-agnostic** – built to work offline, across LAN or USB tethered devices

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
