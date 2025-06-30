# 🛠️ INSTALL_POLICY.md  
_DARF Node Installation & Policy Enforcement Guide_

**Policy Version**: 1.0  
_Last updated: June 29, 2025_

---

## 🚚 Installation Overview

DARF nodes are Android-based render agents. Each installation must meet the following criteria:

- Proper APK deployment and signature validation  
- Writable mount point for incoming jobs  
- Optional security keypair or auth token for controller binding  
- System permissions for file I/O and network upload

Installations should be tested with a minimal payload before being registered.

---

## 🧩 Node Validation Checklist

Before a node is accepted into a render swarm:

- ✅ Device matches approved hardware profile or whitelist  
- ✅ DARF service responds to `ping` and `version` calls from controller  
- ✅ Disk write speed exceeds baseline minimum  
- ✅ Time sync (NTP) is within ±3 sec of controller  

Failure on any of the above triggers quarantine or sandbox mode.

---

## 🔒 Policy Enforcement

Nodes will **reject** execution under the following conditions:

- Invalid signature or expired controller token  
- Firmware below minimum supported Android version  
- Mount point unreachable, unwritable, or full  
- Disallowed background processes detected (configurable list)  

All violations are logged locally **and** reported upstream.

---

## ⚙️ Configuration Flags

These can be set via environment variables or `config.json`:

| Flag Name            | Description                                | Default |
|----------------------|--------------------------------------------|---------|
| `DARF_STRICT_MODE`   | Enforces all policy rules strictly         | `true`  |
| `NODE_DEBUG_LOGS`    | Enables verbose logging                    | `false` |
| `DISABLE_QUARANTINE` | Allow node to run even after policy breach | `false` |

Use caution with overrides—misconfigurations could lead to untrusted renders.

---

## 📝 Logging + Audit Trail

Each node maintains:

- `/darf/logs/install.log` for install and onboarding events  
- `/darf/logs/runtime.log` for job attempts, errors, and warnings  
- Optional remote logging via webhook or controller relay  

Audit retention minimum: **30 days**

---

## 📌 Notes

- DARF does not auto-update. Manual validation is required per patch release  
- Nodes may silently disable features not supported by current firmware  
- Controllers may assign temporary policies for testing or staging environments
```

---

## 🧾 Sample Configuration (`config.json`)

This example shows default enforcement flags for a production-ready DARF node:

```json
{
  "DARF_STRICT_MODE": true,
  "NODE_DEBUG_LOGS": false,
  "DISABLE_QUARANTINE": false
}
```

DARF_STRICT_MODE: When true, all validation and policy rules are enforced rigidly. Set to false only for controlled test environments.

NODE_DEBUG_LOGS: Enables verbose logging for troubleshooting. Recommended only during installation or diagnostics.

DISABLE_QUARANTINE: When true, allows the node to remain active even after failing validation. Use with caution—typically reserved for dev or staging contexts.
