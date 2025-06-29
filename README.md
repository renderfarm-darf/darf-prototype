# DARF – Distributed Android Render Farm

DARF is a conceptual framework in active development. It invites developers to shape a native, distributed rendering system for Android from the ground up—exploring hardware-level orchestration across mobile devices, offline or in the cloud.


## ⚙️ Core Concept  
DARF is:

📱 **Android-first and native** – no Linux layers or emulators; built directly for Android hardware  
🖥️ **PC-coordinated** – render jobs are created and dispatched from desktop apps  
🛠️ **Renderer-agnostic** – supports any CLI-based renderer (e.g., Blender, FFmpeg, others)  
🔌 Flexible networking – designed for offline rendering via LAN or USB, with future support for cloud-based input/output workflows


## 🚧 Current Focus

We’re beginning with integration around **Blender CLI rendering**, using Python scripts to prepare frame-based render jobs and dispatch them to Android nodes via DARF.

Key priorities:

- Define minimal task packet format (scene files, frame ranges, render commands)
- Prototype task dispatcher for Windows/macOS/Linux
- Develop lightweight Android-side agent to execute jobs and return output

## 🔭 Roadmap Highlights  
See the full [ROADMAP.md](./docs/ROADMAP.md) for details, but here's a quick glimpse:

👷 PC-driven task queue system (dispatch → Android nodes)  
🔄 Batch render support from:  
• Blender (active)  
• FFmpeg (in queue)  
• After Effects / Resolve / C4D (planned)  
💾 Asset caching and retry logic (offline-friendly, cloud-optional)  
📊 Basic dashboard or CLI tool for task monitoring  
🔐 Encrypted asset transport for secure job delivery  
📱 DIRF expansion (Distributed iOS Render Farm) as a native Swift sibling—no porting, all new build

## 🤝 Contributing

DARF welcomes thoughtful, curious developers who want to:

- Experiment with render pipelines beyond the cloud  
- Reclaim old Android hardware for creative workflows  
- Extend or adapt task runners for specific tools and environments

We encourage forks, discussions, and pull requests.

See [CONTRIBUTING.md](./verified-scenes/CONTRIBUTING.md) and join the conversation under GitHub Discussions.

## 🧪 Who It’s For  
DARF isn’t for end users—not yet.

This is for developers, students, hobbyists, pipeline designers, and creative technologists who aren’t afraid to poke the edges of what render workflows could become.

If that’s you, welcome in.
## 📜 License

This project is licensed under the [GNU General Public License v3.0](./LICENSE).  
Use it, modify it, share it—just keep it open.

---

**Made by weird people with old phones and wild render dreams.**
