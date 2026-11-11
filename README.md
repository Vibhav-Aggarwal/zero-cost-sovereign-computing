# Zero-Cost Sovereign Computing — reference configuration

[![Paper DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19654425.svg)](https://doi.org/10.5281/zenodo.19654425)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0000--7686--7119-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0000-7686-7119)

Reference configuration and companion artifact for the heterogeneous sovereign compute cluster described in:

> Aggarwal, V. (2026). *Zero-Cost Sovereign Computing: A Reproducible Multi-Node Cluster from mDNS, a Mesh VPN, Cloud Tunnels, and Free-Tier VPSs.* (Version 2). Zenodo. https://doi.org/10.5281/zenodo.19654425

The complete publication-ready Version 2 manuscript is archived in this repository:
📄 **[aggarwal-2026-zero-cost-sovereign-computing-v2.pdf](aggarwal-2026-zero-cost-sovereign-computing-v2.pdf)**

---

## What this repo contains

All secrets, credentials, keys, real hostnames, and personal data have been strictly redacted and replaced with descriptive placeholders. The configurations here are a starting-point *template*, not an active deployment.

```
zero-cost-sovereign-computing/
├── README.md                                    (this file)
├── aggarwal-2026-zero-cost-sovereign-computing-v2.pdf  (Version 2 publication PDF)
├── LICENSE                                      (CC BY 4.0)
├── CITATION.cff                                 (Machine-readable citation metadata)
├── headscale/
│   ├── config.yaml.example                      (Sanitized Headscale v0.28 config)
│   └── acl.hujson.example                       (User + node-level ACL policy)
├── cloudflared/
│   └── config.yml.example                       (Per-node tunnel with ingress rules)
├── mcp-proxy/
│   ├── mcp-server.service                       (systemd unit for mcp-proxy)
│   └── env.example                              (Allowed-directory list template)
├── scripts/
│   └── bootstrap-node.sh                        (Minimal bootstrap script for Ubuntu)
└── diagrams/
    ├── fig1-topology.mmd                        (Mermaid source of Figure 1)
    ├── fig2-mcp-federation.mmd                  (Mermaid source of Figure 2)
    └── fig4-headscale-flow.mmd                  (Mermaid source of Figure 4)
```

---

## Key Highlights (Version 2 Refresh)

- **11 Heterogeneous Nodes**: Predominantly repurposed, secondhand, and minimal-new hardware spanning 5 segments: **Cloud · Lab · Office · Home · Nomadic** (including an added `test-server` node on a secondhand 2014 Mac mini).
- **Invoice-Verified Capital Accounting**: Marginal hardware capital to assemble the cluster is **≈ ₹51,525 (≈ USD 625)**, against a historical acquisition cost across prior owners and uses of **≥ USD 13,000**.
- **Recurring Cloud Fees**: Driven to roughly **₹300/month (≈ USD 3.60/month)**.
- **Continuous Operation**: Over **20 months** of verified production operation (February 2025 – October 2026).
- **Three-Plane Addressing**: Zero-configuration LAN discovery (`.local` mDNS/Avahi) → Mesh VPN (`100.64.0.0/10` via Headscale) → Cloudflare Tunnels (public ingress).
- **Agentic AI Federation**: Federation of seven Model Context Protocol (MCP) server endpoints enabling autonomous tool access across nodes.
- **Measured Network Benchmarks**: Includes route latency and throughput comparisons across LAN, direct tailnet, DERP relay, and Cloudflare access paths (§6.4).

---

## Cite

```bibtex
@article{aggarwal_2026_zerocost_v2,
  author       = {Aggarwal, Vibhav},
  title        = {{Zero-Cost Sovereign Computing: A Reproducible Multi-Node Cluster from mDNS, a Mesh VPN, Cloud Tunnels, and Free-Tier VPSs}},
  year         = 2026,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.19654425},
  url          = {https://doi.org/10.5281/zenodo.19654425}
}
```
