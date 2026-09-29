# Infrastructure Holocron Architecture

This document describes the current-state architecture of the Infrastructure Holocron environment.

## Current-State Architecture

```mermaid
flowchart TD
    A[Trusted Devices<br/>Victus PC / Chromebook] --> B[Private Home Network]

    B --> C[iDRAC 8 Enterprise<br/>Remote Management]
    B --> D[Dell PowerEdge R630<br/>Proxmox VE 9.0.3<br/>128 GB RAM / RAID 10]

    D --> E[VM 100 - lloyd-rhel01<br/>RHEL 9.8<br/>8 vCPU / 16 GB RAM / 100 GB Disk]

    E --> F[SSH Administration]
    E --> G[QEMU Guest Agent]
    E --> H[Podman]

    H --> I[Ollama<br/>Local AI Runtime]
    H --> J[Open WebUI<br/>Browser Chat Interface]

    J <--> I

...
