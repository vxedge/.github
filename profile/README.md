## vxedge: an open SDV network-slicing testbed

vxedge maps **5G network slices onto zonal and central software-defined-vehicle (SDV) E/E
architectures**, entirely in software, on one machine. Every published number ships with the
manifest and image digests that produced it.

- **vxgateway** is a software-defined edge gateway (bridge/OVS VLANs, tc queue trees, WireGuard, VXLAN), with real S-NSSAI slicing through Open5GS and UERANSIM.
- **Virtual ECUs** run on QEMU/KVM via libvirt or raw-QEMU microVMs, and **central compute** runs in containers.
- **vxAPI** is an API-first Rust control plane (gRPC/Protobuf). The `vxedge` CLI and an MCP server are thin clients over it.
- **Everything is driven by manifests**, from a single experiment up to a full software-bootstrapped vehicle.

### Results so far

| Hypothesis | Verdict |
|---|---|
| H1: VLAN + tc reservations isolate the ADAS slice under infotainment load | **Holds**: p99 0.91× baseline |
| H2: real S-NSSAI slicing vs static VLAN mapping | **Holds** |
| H3: virtual-ECU packaging affects latency | **Holds**: virtio transport dominant |
| H4: co-located OTA leaves the ADAS slice SLA intact | **Holds** |

Every number: [FACTS.md](https://github.com/vxedge/docs/blob/main/FACTS.md) ·
Details: [RESULTS.md](https://github.com/vxedge/docs/blob/main/RESULTS.md) ·
Roadmap: [ROADMAP.md](https://github.com/vxedge/docs/blob/main/ROADMAP.md)

### Repositories

| | |
|---|---|
| [**vxedge**](https://github.com/vxedge/vxedge) | Control plane, vxAPI, CLI, vxgateway (**start here**) |
| [vxperiments](https://github.com/vxedge/vxperiments) | Experiments, analysis, frozen results |
| [vxagents](https://github.com/vxedge/vxagents) · [vxtelemetry](https://github.com/vxedge/vxtelemetry) | Measurement agents · telemetry and archiving |
| [vxota](https://github.com/vxedge/vxota) | OTA server (the H4 workload) |
| [vxparts](https://github.com/vxedge/vxparts) | OCI/ORAS registry of every loadable |
| [vxmodels](https://github.com/vxedge/vxmodels) | SysML v2 models and the manifest renderer |
| [vxmcp](https://github.com/vxedge/vxmcp) | MCP server over vxAPI |
| [docs](https://github.com/vxedge/docs) | Architecture, getting started, user guide |

Site: **[vxedge.dev](https://vxedge.dev)** · Contact: hello@vxedge.dev ·
Apache-2.0 (code), CC BY 4.0 (docs and results)
