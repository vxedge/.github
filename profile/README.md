<p align="center">
  <a href="https://vxedge.dev">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/vxedge/.github/main/profile/vxedge-lockup-light.png">
      <img alt="vxedge" src="https://raw.githubusercontent.com/vxedge/.github/main/profile/vxedge-lockup-ink.png" width="280">
    </picture>
  </a>
</p>

<h3 align="center">Experiment with the vehicle before it exists.</h3>

<p align="center">
  <a href="https://vxedge.dev">Website</a> ·
  <a href="https://vxedge.dev/how/">How it works</a> ·
  <a href="https://vxedge.dev/results/">Evidence</a> ·
  <a href="https://vxedge.dev/docs/">Docs</a> ·
  <a href="https://vxedge.dev/collaborate/">Collaborate</a>
</p>

vxedge is an open, agent-operable testbed for software-defined vehicles. A vehicle is declared as
code, run on one machine, and measured: **5G network slices onto zonal and central E/E
architectures**, entirely in software. Every published number ships with the manifest and image
digests that produced it.

**Status:** pre-release (0.x). Phases 1–2 are complete and phase 3 is in progress. The manifest
schema and vxAPI may change between minor versions; published results are frozen.

### Results so far

| Hypothesis | Verdict |
|---|---|
| H1: VLAN + tc reservations isolate the ADAS slice under infotainment load | **Holds**: p99 0.91× baseline |
| H2: real S-NSSAI slicing vs static VLAN mapping | **Holds** |
| H3: virtual-ECU packaging affects latency | **Holds**: virtio transport dominant |
| H4: co-located OTA leaves the ADAS slice SLA intact | **Holds** |

Every number is registered in [FACTS.md](https://github.com/vxedge/docs/blob/main/FACTS.md);
details and caveats are in [RESULTS.md](https://github.com/vxedge/docs/blob/main/RESULTS.md) and the
[roadmap](https://github.com/vxedge/docs/blob/main/ROADMAP.md).

### Repositories

The repositories are being opened in order, starting with the documentation. Each link below goes
live as its repository is published.

| Repo | What |
|---|---|
| [**docs**](https://github.com/vxedge/docs) | Specification, results, user guide and the facts registry (**start here**) |
| [**vxedge**](https://github.com/vxedge/vxedge) | Control plane, vxAPI, CLI and vxgateway |
| [**vxperiments**](https://github.com/vxedge/vxperiments) | Experiments, analysis and frozen results |
| vxagents · vxtelemetry | Measurement agents · telemetry and archiving |
| vxota | OTA server (the H4 workload) |
| vxparts | OCI/ORAS registry of every loadable |
| vxmodels | SysML v2 models and the manifest renderer |
| vxmcp | MCP server over vxAPI |

Contact: [hello@vxedge.dev](mailto:hello@vxedge.dev) · Security: [security@vxedge.dev](mailto:security@vxedge.dev) ·
Code is Apache-2.0; docs, results and figures are CC BY 4.0. © The vxedge Authors.
