# Day 02 – Virtualization Concepts

## Recap of Virtualization
Virtualization is a technology that allows multiple virtual machines (VMs) to run on a single physical machine. Each VM can run its own operating system and applications independently.

It helps organizations use hardware resources efficiently and reduce infrastructure costs.

---

## Components of Virtualization

### 1. Host Machine
The physical computer that provides resources such as CPU, RAM, storage, and network to virtual machines.

Example:
A laptop or server running virtualization software.

---

### 2. Guest Machine
A virtual machine that runs inside the host system.  
Each guest machine behaves like a separate computer.

Example:
Running Ubuntu and Windows on the same physical system.

---

### 3. Hypervisor
The hypervisor is software that manages virtual machines.  
It allocates system resources and ensures that VMs run independently.

Functions of Hypervisor:
- Creates virtual machines
- Allocates CPU, RAM, and storage
- Manages communication between VMs and hardware

---

## Types of Hypervisors

### Type 1 Hypervisor (Bare Metal)
Runs directly on the hardware without an operating system.

Advantages:
- Better performance
- More secure
- Used in data centers

Examples:
- VMware ESXi
- Microsoft Hyper-V
- Xen

---

### Type 2 Hypervisor (Hosted)
Runs on top of an existing operating system.

Advantages:
- Easy to install
- Good for testing and learning

Examples:
- VirtualBox
- VMware Workstation

---

## Benefits of Virtualization

1. Better Hardware Utilization  
   Multiple systems can run on one physical machine.

2. Cost Reduction  
   Fewer physical servers are required.

3. Isolation  
   Problems in one VM do not affect other VMs.

4. Scalability  
   New virtual machines can be created quickly.

5. Easy Testing Environment  
   Developers can test software in different operating systems.

---

## Example Scenario

A computer with:
- 16 GB RAM
- 1 TB Storage

Using virtualization, it can run:

- Ubuntu VM (4 GB RAM)
- Windows VM (6 GB RAM)
- Kali Linux VM (4 GB RAM)

All simultaneously on one physical machine.

---

## Conclusion
Virtualization is a key technology in modern IT infrastructure and is widely used in cloud computing, DevOps, and server management.