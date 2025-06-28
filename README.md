# DARF – Distributed Android Render Farm

**DARF is for creators. Built by necessity, shared by design.**

DARF is a render-node prototype that distributes animation tasks across recycled Android phones.  
While the initial prototype uses Blender CLI for testing, the architecture is renderer-agnostic—designed to support any command-line-capable animation, video, or compositing tool.

## Why DARF?

To empower indie creators, students, and hobbyists who need render power but don’t have a studio budget.  
DARF exists to prove that with a handful of mobile devices and a bit of coordination, anyone can build a distributed render system from scratch.

## Current Status

- Single-node testing on Android devices
- Blender CLI rendering confirmed
- Repository initialized with open-source license (GPLv3)
- README and documentation scaffolding in progress

## Planned Features

- Multi-node orchestration with device discovery
- Render queue management and result syncing
- Support for additional engines (FFmpeg, OpenToonz, Krita, Natron)
- Web-based dashboard (future stretch goal)

## License

DARF is licensed under the GNU General Public License v3.0 – open, forever.
