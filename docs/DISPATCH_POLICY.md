# 📤 DISPATCH_POLICY  
_Dispatch Protocols & Policy Enforcement for DARF_

---

## 🚦 Overview

DARF’s dispatch logic defines how the controller assigns frame-layer tasks to eligible Android render nodes. This policy governs:

- 💾 Payload validation
- 🔍 Node eligibility checks
- 🔄 Task assignment logic
- 🧱 Hard failure handling (retry, queue, skip)

Dispatch is never automatic. It is intentional, observable, and enforceable.  

---

## 🗂️ Dispatch Lifecycle

1. **Payload Received**
   - `render_payload.json` is validated against [`RENDER_PAYLOAD_SPEC.md`](./RENDER_PAYLOAD_SPEC.md)
   - Frame layers are split into discrete render tasks
2. **Node Verification**
   - Each connected Android node is checked against `INSTALL_POLICY.md`
   - Devices may be:
     - Accepted (eligible, idle)
     - Ignored (SIM active or background use detected)
     - Rejected (ineligible, disallowed model or thermal profile)
3. **Task Assignment**
   - Frames dispatched to one node at a time
   - Dispatch order follows `SCATTER_POLICY.md` (e.g. round-robin, thermal-aware)
4. **Acknowledgment**
   - Node confirms receipt of payload
   - Task enters `active` state
5. **Monitoring**
   - Node heartbeat monitored for duration
   - Output image logs and metadata begin streaming back
6. **Completion or Requeue**
   - Success: frame marked as `done`
   - Failure: task returned to queue with delay logic
   - Hard fail: task marked `manual_review`

---

## 🛡️ Dispatch Constraints

- A node **must be idle** to receive a new task
- A node **must not process more than 1 frame at a time**
- Render tasks **must not exceed timeout value** defined in controller settings
- Nodes marked as `throttling`, `hot`, or `SIM_ACTIVE` are automatically skipped
- No node may be assigned frames unless its **eligibility hash has been verified**

---

## 🧠 Optimization & Soft Biasing (Upcoming)

Future versions will include:
- **Device score weighting** (prefer proven fast/thermal-stable devices)
- **Scene-aware hints** (e.g. use flagship node for heavy layers)
- **Pause/Resume APIs** for interactive dispatch throttling

These are governed in [`SCATTER_POLICY.md`](./SCATTER_POLICY.md) and not active during Phase 2.

---

## 🧪 Developer Notes

- All dispatched payloads should be signed if encryption is enabled
- Dispatch logs must include:
  - `frame_id`
  - `layer_key`
  - `target_device_id`
  - `start_time`, `end_time`
- No retry more than 2x unless node pool has fewer than 3 available devices

---

DARF doesn’t rush frames. It delegates them wisely.  
Dispatch is a privilege, not a promise.
