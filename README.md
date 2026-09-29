# The Infrastructure Holocron

**Private infrastructure. Open engineering.**

The Infrastructure Holocron is my hands-on engineering lab for virtualization, Linux systems, network architecture, automation, CI/CD, hybrid cloud, and practical AI operations. It is built on refurbished enterprise hardware and designed to demonstrate how services are deployed, secured, observed, troubleshot, documented, and recovered.

> **Project status:** Working local virtualization and AI foundation. Documentation and current-state verification in progress. Additional integrations below are planned, not presented as completed.

## What is running

- **Compute:** Dell PowerEdge R630 with dual Intel Xeon processors and 128 GB RAM.
- **Virtualization:** Proxmox VE, hosting a Red Hat Enterprise Linux 9.8 virtual machine.
- **Application platform:** Podman containers and locally hosted Ollama inference.
- **AI interface:** Open WebUI and a custom local assistant persona, **L.L.O.Y.D.** (*Loyal, Logical Operations and Your Digital Guardian*).
- **Operations:** SSH administration, QEMU Guest Agent integration, a local baseline VM backup, and an evolving operations runbook.

Lloyd is **my private personal assistant**, not a public chatbot or a public endpoint. The project may demonstrate engineering patterns used in his deployment, but his personal data, credentials, private configuration, and live management interfaces are not published.

## Architecture (current)

```text
                        Private home network
  +--------------------------------------------------------------+
  | Dell PowerEdge R630                                           |
  |  Proxmox VE                                                   |
  |   +------------------------------------------------------+   |
  |   | RHEL VM                                              |   |
  |   |  Podman  -->  Ollama  -->  local Lloyd model          |   |
  |   |       \-->  Open WebUI (authenticated LAN interface)|   |
  |   +------------------------------------------------------+   |
  |  iDRAC: separate hardware management                         |
  +--------------------------------------------------------------+
```

*This is a conceptual view, not a network configuration export. The actual container-network settings and autostart configuration are being audited.*

## Engineering disciplines

| Area | Current demonstration | Planned extension |
|---|---|---|
| Systems and virtualization | Proxmox, RHEL VM, guest integration | Additional Windows/Linux test VMs |
| Containers and AI | Podman, Ollama, local model, Open WebUI | Scoped infrastructure-monitoring agent |
| Operations and recovery | Troubleshooting records, local VM baseline backup | Off-host backups and restore testing |
| Automation and CI/CD | Git installed, repository design in progress | Automated testing, Ansible and controlled deployments |
| Networking and security | Private lab and separated management interfaces | Verified firewall policy, segmented lab, optional hybrid connectivity |
| Cloud engineering | Architecture planning | Terraform-managed AWS test environment |

## Design principles

1. **Separate personal AI from engineering experiments.** Lloyd's private runtime and personal knowledge remain distinct from future public portfolio deployments.
2. **Publish code, not access.** Only sanitized documentation, reusable examples, and non-sensitive source belong in this repository.
3. **Use least privilege.** Monitoring should be read-only; deployment identities should have narrow permissions and explicit approval boundaries.
4. **Document and verify.** Every substantive change should capture purpose, configuration, tests, failure modes, and rollback or recovery steps.
5. **Be precise about progress.** Planned capabilities are labeled as planned until verified in the lab.

## Build milestones

- [x] Configure enterprise host and Proxmox virtualization
- [x] Deploy RHEL guest and confirm guest-agent/SSH access
- [x] Run local Ollama and a custom Lloyd persona
- [x] Deploy an Open WebUI interface
- [x] Create a local VM baseline backup
- [ ] Audit current services, security settings and restart behavior
- [ ] Export sanitized architecture diagram and deployment notes
- [ ] Create a verified off-host backup and perform a restore test
- [ ] Develop a least-privilege, read-only Proxmox monitoring integration
- [ ] Add separate development and deployment environments
- [ ] Build tested GitHub CI workflows and controlled local deployment
- [ ] Implement a separately secured AWS infrastructure-as-code exercise

## Documentation approach

The detailed operational build record—including real IP addresses, troubleshooting notes, account setup, storage configuration, and recovery procedures—is maintained **privately**. This public repository will contain sanitized architecture, reusable automation, verification examples, and lessons learned that are safe to share.

**Note:** No credentials, personal files, model chat history, private addressing, or live administrative access are needed to reproduce the public examples.

## Next milestone

Before expanding the lab, verify the current configuration against the running systems and publish a sanitized architecture diagram with a tested deployment and restart runbook.
