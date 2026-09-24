# Security Policy

vxedge is a research testbed built from real, unmodified networking and virtualization
components (OVS, Linux bridging, tc, WireGuard, FRR, QEMU/KVM, libvirt, Open5GS, UERANSIM), not a
production system — but it runs real kernel networking and real guest OSes, and a vulnerability
in the control plane (`vxedged`, the vxAPI surface, or the CLI) is worth reporting properly.

## Supported versions

| Version | Supported |
|---|---|
| `v0.1.0` and later tags | Yes |
| Pre-release / `main` (unreleased) | Best-effort |

This project is phase-gated ([`docs/ROADMAP.md`](https://github.com/vxedge/docs/blob/main/ROADMAP.md)); a "supported version" table will grow more
granular once there is more than one tagged release line to maintain.

## Reporting a vulnerability

**Do not open a public issue for a security report.** Either use GitHub's private vulnerability
reporting (the repository's **Security → Report a vulnerability** tab) or email
**security@vxedge.dev** with:

- A description of the vulnerability and its impact.
- Steps to reproduce, ideally against a specific tagged release.
- Whether it affects the control plane (`vxedged`/vxAPI), a provisioning path (vxgateway
  netlink/OVS/tc, libvirt XML), a service (`vxota`, `vxtelemetry`), or an agent (`vxagents`).

## Response targets

- **Acknowledgement within 5 business days.**
- **Initial assessment within 15 business days** — whether it's confirmed, its severity, and a
  rough remediation timeline.
- **Disclosure within 90 days** of the initial report, or sooner once a fix ships — standard
  90-day coordinated-disclosure window. If a fix needs longer, we'll say so and why, not go
  silent.

## Scope notes specific to this project

- **Manifests are trusted input**, not attacker-controlled by design — vxedge's threat model
  assumes the operator running `vxedge experiment up` controls the manifest. A vulnerability
  that requires an already-malicious manifest to trigger is lower severity than one reachable
  from network input the gateway actually processes.
- **Third-party components** (QNX, AAOS, CARLA, Autoware, DeepStream/TensorRT, SONiC-VS,
  Open5GS, UERANSIM) have their own upstream security
  processes; report vulnerabilities in those components to their maintainers, not here, unless
  the issue is specifically in how vxedge integrates or provisions them.
