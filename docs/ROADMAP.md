# DARF Roadmap v1.6

_Last updated: June 29, 2025_

DARF (Distributed Android Render Farm) is a modular, headless-rendering ecosystem where Android devices act as individual frame processors coordinated by a centralized controller. This roadmap defines feature phases, boundaries, and future growth without overcommitting early.

---

## 📐 Phase 1: Controller Architecture & Payload Definition

> **No Android devices. No rendering. No simulation. Only structure.**

### Scope
- Build **Controller Interface** (UI + core logic):
  - Import & inspect frame sequences
  - Define and export `render_payload.json` with correct schema
  - Display job queue, frame metadata, task breakdown
- Output analyzed payloads to filesystem (for validation only)
- Define protocols and constraints:
  - Payload lifecycle
  - Node eligibility policies
  - Optimization enforcement structure
- Begin documentation:
  - `DISPATCH_POLICY.md`
  - `INSTALL_POLICY.md`
  - `OPTIMIZATION_BLOCKERS.md`
  - `NODE_BEHAVIOR.md`
  - `RENDER_PAYLOAD_SPEC.md`

### Out-of-Scope
- ❌ No Android connectivity  
- ❌ No rendering or simulation  
- ❌ No device handshake  
- ✅ All testing is structural, file-based, and static

---

## 🚦 Phase 2: Android Node Activation & Basic Dispatch

> **Rendering begins. Android renderer boots as headless daemon.**

- Controller begins node pairing & payload dispatch
- Android renderer receives parsed frame-layer tasks:
  - Starts on boot
  - No user interface
  - Processes payload, logs output
- Basic frame return & status tracking  
- Enforced per-device hardcoded pause (`pause_after_first_frame_ms`)  
- No retry logic yet—failures are logged only

---

## 🔁 Phase 3: Mesh Coordination & Recovery

> **DARF becomes aware of its mesh. And guards it.**

- Node states: idle, rendering, unresponsive, overheated
- Re-queue logic for failed or missed render tasks
- Log synchronization from Android → Controller
- Begin profiling render duration for each node
- Establish `NODE_STATE.md` + `FAILOVER.md`

🔓 *After Phase 3: Controlled alpha testing for trusted users begins.*

---

## 🔧 Phase 4: Enforcement & Runtime Policies

> **Now the system defends itself.**

- Controller enforces optimization tier at payload level
- Android devices:
  - Detect SIM activity (deny install on in-use phones)
  - Lock brightness, kill background tasks (in `Dedicated` mode)
  - Boot directly into renderer—no launcher icon
- Finalize:
  - `ELIGIBILITY_POLICY.md`
  - `DEDICATED_MODE.md`

---

## 🖼️ Phase 5: 2D Layer Support & Compositing Passes

- Accept 2D-oriented `render_payload.json` from:
  - Krita
  - Toon Boom
  - AE / Blender image sequences
- Android node performs post-layer operations:
  - Filtering
  - Compositing
  - Tone mapping
- Payload schema extended to identify render type

---

## ⚛️ Phase 6: Advanced Scheduling & Scatter Policy

- Dynamic task distribution:
  - Thermal-aware
  - Round-robin
  - Flagship bias
- Begin optional `CoreSplit`: intra-frame parallelism on multi-core nodes
- Per-node render history and cooldown modeling
- Docs:
  - `SCATTER_POLICY.md`
  - `CORE_SPLIT.md`

---

## 🛰️ Phase 7+: Long-Horizon Features

| Feature | Status |
|--------|--------|
| Gold Mesh Tier (cluster profiling) | Drafting |
| Multi-frame queueing per flagship node | Concept |
| `DARF Calc`: ROI vs cloud renderer estimator | In discussion |
| Cloud spillover mode (hybrid dispatch) | Frozen |
| Contributor manifest + philosophy docs | Writing |

---

## 📌 Notes

- ⚙️ **Controller thermal_independent = true** — it doesn’t throttle; it dispatches  
- ✅ **If you can run Blender, you can run DARF**  
- 🤝 Public alpha testing opens only *after Phase 3* completion  
- 💾 Android renderer target footprint: **<12 MB**, with RAM peak ~400 MB per task  
- 🔒 Thermal limits and device eligibility are hard rules—not toggles  

---

## 📁 Suggested Docs Folder Layout

```plaintext
/docs
  ├── ROADMAP.md
  ├── DISPATCH_POLICY.md
  ├── RENDER_PAYLOAD_SPEC.md
  ├── NODE_BEHAVIOR.md
  ├── INSTALL_POLICY.md
  ├──
