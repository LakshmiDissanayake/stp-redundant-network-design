# STP-Based Redundant Network Design

## Project Overview

This project demonstrates the design and implementation of a redundant switched network using Cisco Packet Tracer. It focuses on improving network reliability and preventing Layer 2 switching loops through Spanning Tree Protocol (STP).

The network consists of three interconnected Cisco Catalyst 3560 multilayer switches arranged in a triangle topology, with five end devices distributed across two VLANs.

The project explores how STP manages redundant links, elects a Root Bridge, selects forwarding and blocking ports, and maintains network connectivity when a link fails.

## Technologies Used

- Cisco Packet Tracer
- Cisco Catalyst 3560 Multilayer Switches
- Spanning Tree Protocol (STP)
- Per-VLAN Spanning Tree Plus (PVST+)
- Virtual LANs (VLANs)
- IEEE 802.1Q Trunking
- Cisco IOS CLI

## Network Topology

The network uses a triangle topology connecting three switches. Each switch has redundant connections to the other switches, providing alternative paths for network communication.

Five PCs are connected to the switches and assigned to two separate VLANs.

**Network components:**
- 3 Cisco Catalyst 3560 multilayer switches
- 5 PCs
- Redundant inter-switch connections
- VLAN 10 – Sales Department
- VLAN 20 – HR Department

## IP Addressing Plan

| Device | VLAN | IP Address | Subnet Mask |
|---|---|---|---|
| PC0 | 10 | 192.168.10.10 | 255.255.255.0 |
| PC3 | 10 | 192.168.10.11 | 255.255.255.0 |
| PC1 | 10 | 192.168.10.12 | 255.255.255.0 |
| PC4 | 20 | 192.168.20.10 | 255.255.255.0 |
| PC2 | 20 | 192.168.20.11 | 255.255.255.0 |

## Implementation and Configuration

### 1. Network Topology Setup
- Created a triangle topology using three Cisco Catalyst 3560 switches.
- Connected five PCs to the switches.
- Established redundant inter-switch connections.

### 2. VLAN Configuration
- Created VLAN 10 (SALES).
- Created VLAN 20 (HR).
- Assigned PC-facing switch ports to their respective VLANs.

### 3. Trunk Configuration
- Configured switch-to-switch connections as trunk links.
- Allowed VLANs 10 and 20 across the trunk connections.
- Verified trunk configuration using Cisco IOS commands.

### 4. Spanning Tree Protocol Configuration
- Investigated the default STP operation.
- Identified Root Bridge, Root Ports, Designated Ports, and Alternate/Blocking Ports.
- Configured Switch 0 as the preferred Root Bridge for VLANs 10 and 20.
- Experimented with different bridge priorities to observe Root Bridge election.

### 5. Redundant Link Testing
- Identified redundant links placed in blocking states by STP.
- Disconnected an active inter-switch link.
- Observed STP topology changes and alternative path activation.
- Restored the disconnected link and examined the resulting topology.

### 6. Troubleshooting
- Investigated incorrect VLAN assignments and trunk mismatches.
- Corrected configuration issues.
- Verified network connectivity and STP status.

## Testing and Validation

The following connectivity tests were used:

| Test | Expected Result |
|---|---|
| PC0 to PC3 (VLAN 10) | Successful |
| PC2 to PC4 (VLAN 20) | Successful |
| PC0 to PC2 (Different VLANs) | Unsuccessful without inter-VLAN routing |

Additional verification was performed using Cisco IOS commands:

```bash
show vlan brief
show interfaces trunk
show spanning-tree
show spanning-tree vlan 10
show spanning-tree vlan 20
```

## Key Concepts Demonstrated

- Prevention of Layer 2 switching loops.
- Root Bridge election using Bridge ID and priority.
- Root Port and Designated Port selection.
- Alternate port blocking and forwarding behavior.
- VLAN-based Spanning Tree operation.
- Redundant network paths and fault recovery.
- Network troubleshooting and connectivity verification.

## Project Outcome

Successfully implemented a redundant switched network and explored how Spanning Tree Protocol prevents Layer 2 loops while maintaining alternative paths for network availability.

This project strengthened practical understanding of VLAN configuration, trunking, STP operation, network redundancy, and switching fundamentals.

## Project Files

- Cisco Packet Tracer network simulation (`.pkt`)
- Network topology screenshots
- STP configuration and verification screenshots

---

**Tools:** Cisco Packet Tracer | Cisco IOS | Networking Fundamentals
