# Cybersecurity Home Lab Setup — Phase 1

Phase 1 completed as part of the **NETWORKWALKS August Internship Programme (B082).**

## Objective

Set up the first virtual machine for a cybersecurity home lab using Oracle VirtualBox and Kali Linux.

Phase 1 covered:

- Setting up Oracle VirtualBox
- Importing Kali Linux 2026.2
- Creating a custom NAT network
- Connecting the Kali VM to the custom NAT network
- Configuring static IPv4 settings
- Verifying network and internet connectivity
- Creating a VirtualBox snapshot as a stable recovery point

---

## Environment

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Guest OS | Kali Linux 2026.2 |
| Network Type | NAT Network |
| NAT Network Name | `NatNetwork` |
| Network | `10.0.0.0/24` |
| Kali IPv4 Address | `10.0.0.2/24` |
| Default Gateway | `10.0.0.1` |
| DNS Server | `8.8.8.8` |

---

## 1. Import Kali Linux

Kali Linux 2026.2 was downloaded and imported into Oracle VirtualBox as the first virtual machine in the cybersecurity home lab.

![Kali imported into VirtualBox](screenshots/01-kali-imported-virtualbox.png)

---

## 2. Create the Custom NAT Network

A custom VirtualBox NAT network named `NatNetwork` was created with the following IPv4 network:

```text
10.0.0.0/24
```

The NAT network provides the virtual lab environment with network connectivity while keeping it logically separated from the host's physical network.

![Custom NAT Network](screenshots/02-custom-nat-network.png)

---

## 3. Configure the Kali Network Adapter

The Kali VM's virtual network adapter was attached to the custom NAT network.

Configuration:

- Network Adapter: Enabled
- Attached to: NAT Network
- Network Name: `NatNetwork`
- Virtual Cable: Connected

![Kali Network Adapter](screenshots/03-kali-network-adapter.png)

---

## 4. Configure Kali IPv4 Settings

The Kali VM was configured with manual IPv4 settings.

```text
IP Address:      10.0.0.2
Prefix Length:   /24
Default Gateway: 10.0.0.1
DNS Server:      8.8.8.8
```

![Kali IPv4 Configuration](screenshots/04-kali-ip-configuration.png)

---

## 5. Verify Connectivity

The Kali VM was started after the network configuration was applied.

External network connectivity and DNS resolution were verified by successfully accessing an external website from the Kali VM.

![Kali Connectivity Verification](screenshots/05-kali-connectivity-test.png)

---

## 6. Create a Stable Snapshot

After confirming that the Kali VM and its network configuration were functioning correctly, a VirtualBox snapshot was created.

The snapshot provides a stable recovery point before making further changes to the lab environment.

![Kali VM Snapshot](screenshots/06-kali-snapshot.png)

---

## Phase 1 Result

Phase 1 of the Cybersecurity Home Lab Setup was completed successfully.

At the end of this phase, the Kali Linux VM is:

- Imported and operational
- Connected to the custom NAT network
- Configured with a static IPv4 address
- Able to access external network resources
- Backed up with a VirtualBox snapshot

---

## Next Phase

The home lab will be expanded with additional virtual systems:

- Windows
- Android

These systems will be integrated into the lab environment during the next phase of the project.
