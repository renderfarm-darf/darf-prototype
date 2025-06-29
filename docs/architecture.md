# DARF Architecture Notes

# DARF Architecture

> *“A distributed render farm for the everyday artist, not the data center.”*

## 🔧 Core Components
- **Dispatcher**: Orchestrates render tasks to connected devices
- **Render Nodes**: Android-powered endpoints that execute frames
- **Scene Validation**: Ensures tasks are safe and predictable for low-end clients

## 📡 Communication Flow
- WebSocket? HTTP? Shared Queues? (TBD)
- Minimal centralization, max portability

## 📦 File Handling
- Assets prepped for chunking, streaming, or direct download
- Compression & fallback strategies (low spec device priority)

## 🛠️ Future Ideas
- Plugin support for Blender, Godot, etc.
- Android-native agent
- Offline-first node behavior

## 💬 Notes
This doc evolves as ideas do. Suggest edits or raise ideas in Discussions!
