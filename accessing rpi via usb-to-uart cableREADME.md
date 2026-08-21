# Raspberry Pi 4B UART Serial Console Setup 

## 1. Connections

| **UART Cable** | **RPI(Pin)** |
| -------------- | ------------ |
| Black          | GND/ Pin 6   |
| White          | Pin 8        |
| Green          | Pin 10       |

## 2. Connect USB UART to Laptop
## 3. Power On Raspberry Pi
## 4. Open Tera Term
### Serial Port Settings
   - Make sure the baud rate is set to 115200.
   - Data bits: 8
   - Parity: None
   - Stop bits: 1
   - Flow control: None
### Confirm COM Port
   - Check the Device Manager that the COM port (COM6) is assigned to your USB-to-Serial adapter.
   - Select this COM6 port in Tera Term.
### Press Enter
   - Sometimes the terminal screen stays blank until you press Enter key, which triggers a prompt from the Raspberry Pi.
### Close Other Applications
   - Close all other programs which might be using the COM port (other terminal emulators, IDEs, etc.) that can block Tera Term from accessing the port.
### Run Tera Term as Administrator
   - Right-click Tera Term icon -> Run as administrator, to avoid permission issues.
### Test Loopback
    - Disconnect from Raspberry Pi.
    - Short RX and TX pins on the USB-to-Serial cable.
    - Open Tera Term on the COM port.
    - Try typing; you should see echoed characters.
    - If there is no echo, there is a problem with the serial adapter or cable.
### Try Another Terminal Program
    - Use another terminal emulator like PuTTY or CoolTerm to cross-check.
### Check Wiring and Power
    - Verify the correct wiring: RX to TX, TX to RX, GND to GND.
    - Ensure Raspberry Pi is powered on.

## Expected Output

```text
pi@raspberrypi:~$    [    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd083]
[    0.000000] Linux version 6.12.34+rpt-rpi-v8 (serge@raspberrypi.com) (aarch64-linux-gnu-gcc-12 (Debian 12.2.0-14+deb12u1) 12.2.0, GNU ld (GNU Binutils for Debian) 2.40) #1 SMP PREEMPT Debian 1:6.12.34-1+rpt1~bookworm (2025-06-26)
[    0.000000] KASLR enabled
[    0.000000] random: crng init done
[    0.000000] Machine model: Raspberry Pi 4 Model B Rev 1.5
[    0.000000] efi: UEFI not found.
[    0.000000] Reserved memory: created CMA memory pool at 0x000000000e800000, size 512 MiB
[    0.000000] OF: reserved mem: initialized node linux,cma, compatible id share dma-pool
[    0.000000] OF: reserved mem: 0x000000000e800000..0x000000002e7fffff (524288  KiB) map reusable linux,cma
[    0.000000] OF: reserved mem: 0x000000003ef667c0..0x000000003ef667f5 (0 KiB) nomap non-reusable nvram@0
[    0.000000] OF: reserved mem: 0x000000003ef66580..0x000000003ef6677f (0 KiB) nomap non-reusable nvram@1
[    0.000000] NUMA: Faking a node at [mem 0x0000000000000000-0x000000007fffffff                                                                                                            ]
[    0.000000] Faking node 0 at [mem 0x0000000000000000-0x000000007fffffff] (2048MB)
[    0.000000] NODE_DATA(0) allocated [mem 0x7fbdc300-0x7fbdefff]
[    0.000000] Zone ranges:
[    0.000000]   DMA      [mem 0x0000000000000000-0x000000003fffffff]
[    0.000000]   DMA32    [mem 0x0000000040000000-0x000000007fffffff]
[    0.000000]   Normal   empty
[    0.000000] Movable zone start for each node
[    0.000000] Early memory node ranges
[    0.000000]   node   0: [mem 0x0000000000000000-0x000000003b3fffff]
[    0.000000]   node   0: [mem 0x0000000040000000-0x000000007fffffff]
[    0.000000] Initmem setup node 0 [mem 0x0000000000000000-0x000000007fffffff]
[    0.000000] On node 0, zone DMA32: 19456 pages in unavailable ranges
[    0.000000] percpu: Embedded 33 pages/cpu s95064 r8192 d31912 u135168
[    0.000000] Detected PIPT I-cache on CPU0
[    0.000000] CPU features: detected: Spectre-v2
[    0.000000] CPU features: detected: Spectre-v3a
[    0.000000] CPU features: detected: Spectre-v4
[    0.000000] CPU features: detected: Spectre-BHB
[    0.000000] CPU features: kernel page table isolation forced ON by KASLR
[    0.000000] CPU features: detected: Kernel page table isolation (KPTI)
[    0.000000] CPU features: detected: ARM erratum 1742098
[    0.000000] CPU features: detected: ARM errata 1165522, 1319367, or 1530923
[    0.000000] alternatives: applying boot alternatives
[    0.000000] Kernel command line: coherent_pool=1M 8250.nr_uarts=1 snd_bcm2835                                                                                                             .enable_headphones=0 cgroup_disable=memory numa_policy=interleave nvme.max_host_                                                                                                             mem_size_mb=0 snd_bcm2835.enable_headphones=1 snd_bcm2835.enable_hdmi=1 snd_bcm2                                                                                                             835.enable_hdmi=0  numa=fake=1 system_heap.max_order=0 smsc95xx.macaddr=D8:3A:DD                                                                                                             :F3:D7:2F vc_mem.mem_base=0x3ec00000 vc_mem.mem_size=0x40000000  console=ttyS0,115200 console=tty1 root=PARTUUID=17e43e1f-02 rootfstype=ext4 fsck.repair=yes roo twait cfg80211.ieee80211_regdom=IN
[    0.000000] cgroup: Disabling memory control group subsystem
[    0.000000] mempolicy: NUMA default policy overridden to 'interleave:0'
[    0.000000] Dentry cache hash table entries: 262144 (order: 9, 2097152 bytes,                                                                                                              linear)
[    0.000000] Inode-cache hash table entries: 131072 (order: 8, 1048576 bytes,                                                                                                              linear)
[    0.000000] Fallback order for Node 0: 0
[    0.000000] Built 1 zonelists, mobility grouping on.  Total pages: 504832
[    0.000000] Policy zone: DMA32
[    0.000000] mem auto-init: stack:all(zero), heap alloc:off, heap free:off
[    0.000000] software IO TLB: area num 4.
[    0.000000] software IO TLB: mapped [mem 0x0000000037400000-0x000000003b40000                                                                                                             0] (64MB)
[    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
[    0.000000] ftrace: allocating 45267 entries in 177 pages
[    0.000000] ftrace: allocated 177 pages with 4 groups
[    0.000000] rcu: Preemptible hierarchical RCU implementation.
[    0.000000] rcu:     RCU event tracing is enabled.
[    0.000000]  Trampoline variant of Tasks RCU enabled.
[    0.000000]  Rude variant of Tasks RCU enabled.
[    0.000000]  Tracing variant of Tasks RCU enabled.
[    0.000000] rcu: RCU calculated value of scheduler-enlistment delay is 25 jif                                                                                                             fies.
[    0.000000] RCU Tasks: Setting shift to 2 and lim to 1 rcu_task_cb_adjust=1 r                                                                                                             cu_task_cpu_ids=4.
[    0.000000] RCU Tasks Rude: Setting shift to 2 and lim to 1 rcu_task_cb_adjus                                                                                                             t=1 rcu_task_cpu_ids=4.
[    0.000000] RCU Tasks Trace: Setting shift to 2 and lim to 1 rcu_task_cb_adju                                                                                                             st=1 rcu_task_cpu_ids=4.
[    0.000000] NR_IRQS: 64, nr_irqs: 64, preallocated irqs: 0
[    0.000000] Root IRQ handler: gic_handle_irq
[    0.000000] GIC: Using split EOI/Deactivate mode
[    0.000000] rcu: srcu_init: Setting srcu_struct sizes based on contention.
[    0.000000] arch_timer: cp15 timer(s) running at 54.00MHz (phys).
[    0.000000] clocksource: arch_sys_counter: mask: 0xffffffffffffff max_cycles:                                                                                                              0xc743ce346, max_idle_ns: 440795203123 ns
[    0.000000] sched_clock: 56 bits at 54MHz, resolution 18ns, wraps every 43980                                                                                                             46511102ns
[    0.000151] Console: colour dummy device 80x25
[    0.000159] printk: legacy console [tty1] enabled
[    0.000440] Calibrating delay loop (skipped), value calculated using timer fr                                                                                                             equency.. 108.00 BogoMIPS (lpj=216000)
[    0.000453] pid_max: default: 32768 minimum: 301
[    0.000488] LSM: initializing lsm=capability
[    0.000595] Mount-cache hash table entries: 4096 (order: 3, 32768 bytes, line                                                                                                             ar)
[    0.000616] Mountpoint-cache hash table entries: 4096 (order: 3, 32768 bytes,                                                                                                              linear)
[    0.001929] rcu: Hierarchical SRCU implementation.
[    0.001950] rcu:     Max phase no-delay instances is 1000.
[    0.002088] Timer migration: 1 hierarchy levels; 8 children per group; 1 cros                                                                                                             snode level
[    0.002721] EFI services will not be available.
[    0.002902] smp: Bringing up secondary CPUs ...
[    0.003233] Detected PIPT I-cache on CPU1
[    0.003303] CPU1: Booted secondary processor 0x0000000001 [0x410fd083]
[    0.003655] Detected PIPT I-cache on CPU2
[    0.003689] CPU2: Booted secondary processor 0x0000000002 [0x410fd083]
[    0.004037] Detected PIPT I-cache on CPU3
[    0.004072] CPU3: Booted secondary processor 0x0000000003 [0x410fd083]
[    0.004118] smp: Brought up 1 node, 4 CPUs
[    0.004150] SMP: Total of 4 processors activated.
[    0.004156] CPU: All CPU(s) started at EL2
[    0.004169] CPU features: detected: 32-bit EL0 Support
[    0.004174] CPU features: detected: 32-bit EL1 Support
[    0.004180] CPU features: detected: CRC32 instructions
[    0.004214] alternatives: applying system-wide alternatives
[    0.005062] Memory: 1348224K/2019328K available (14144K kernel code, 2406K rw                                                                                                             data, 4820K rodata, 5440K init, 577K bss, 141416K reserved, 524288K cma-reserved                                                                                                             )
[    0.005390] devtmpfs: initialized
[    0.009358] Enabled cp15_barrier support
[    0.009391] Enabled setend support
[    0.009477] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, ma                                                                                                             x_idle_ns: 7645041785100000 ns
[    0.009495] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
[    0.017929] 2G module region forced by RANDOMIZE_MODULE_REGION_FULL
[    0.017965] 0 pages in range for non-PLT usage
[    0.017968] 517376 pages in range for PLT usage
[    0.018124] pinctrl core: initialized pinctrl subsystem
[    0.018452] DMI not present or invalid.
[    0.019915] NET: Registered PF_NETLINK/PF_ROUTE protocol family
[    0.020596] DMA: preallocated 1024 KiB GFP_KERNEL pool for atomic allocations
[    0.020689] DMA: preallocated 1024 KiB GFP_KERNEL|GFP_DMA pool for atomic all                                                                                                             ocations
[    0.020836] DMA: preallocated 1024 KiB GFP_KERNEL|GFP_DMA32 pool for atomic a                                                                                                             llocations
[    0.020870] audit: initializing netlink subsys (disabled)
[    0.021011] audit: type=2000 audit(0.020:1): state=initialized audit_enabled=                                                                                                             0 res=1
[    0.021237] thermal_sys: Registered thermal governor 'step_wise'
[    0.021256] cpuidle: using governor menu
[    0.021352] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
[    0.021404] ASID allocator initialised with 32768 entries
[    0.021802] Serial: AMBA PL011 UART driver
[    0.024255] /soc/interrupt-controller@40041000: Fixed dependency cycle(s) wit                                                                                                             h /soc/interrupt-controller@40041000
[    0.024659] bcm2835-mbox fe00b880.mailbox: mailbox enabled
[    0.032089] raspberrypi-firmware soc:firmware: Attached to firmware from 2025                                                                                                             -04-30T13:33:39, variant start
[    0.036093] raspberrypi-firmware soc:firmware: Firmware hash is 5560078dcc859                                                                                                             1a00f57b9068d13e5544aeef3aa
[    0.041427] /scb/pcie@7d500000: Fixed dependency cycle(s) with /scb/pcie@7d50                                                                                                             0000
[    0.041527] /scb/pcie@7d500000: Fixed dependency cycle(s) with /scb/pcie@7d50                                                                                                             0000
[    0.044476] bcm2835-dma fe007000.dma-controller: DMA legacy API manager, dmac                                                                                                             hans=0x1
[    0.045155] iommu: Default domain type: Translated
[    0.045165] iommu: DMA domain TLB invalidation policy: strict mode
[    0.045798] SCSI subsystem initialized
[    0.045886] usbcore: registered new interface driver usbfs
[    0.045906] usbcore: registered new interface driver hub
[    0.045926] usbcore: registered new device driver usb
[    0.046096] pps_core: LinuxPPS API ver. 1 registered
[    0.046103] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giome                                                                                                             tti <giometti@linux.it>
[    0.046114] PTP clock support registered
[    0.046681] vgaarb: loaded
[    0.046920] clocksource: Switched to clocksource arch_sys_counter
[    0.442499] VFS: Disk quotas dquot_6.6.0
[    0.442540] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
[    0.445938] NET: Registered PF_INET protocol family
[    0.446103] IP idents hash table entries: 32768 (order: 6, 262144 bytes, line                                                                                                             ar)
[    0.447167] tcp_listen_portaddr_hash hash table entries: 1024 (order: 2, 1638                                                                                                             4 bytes, linear)
[    0.447196] Table-perturb hash table entries: 65536 (order: 6, 262144 bytes,                                                                                                              linear)
[    0.447208] TCP established hash table entries: 16384 (order: 5, 131072 bytes                                                                                                             , linear)
[    0.447264] TCP bind hash table entries: 16384 (order: 7, 524288 bytes, linea                                                                                                             r)
[    0.447741] TCP: Hash tables configured (established 16384 bind 16384)
[    0.447896] MPTCP token hash table entries: 2048 (order: 3, 49152 bytes, line                                                                                                             ar)
[    0.447972] UDP hash table entries: 1024 (order: 3, 32768 bytes, linear)
[    0.447993] UDP-Lite hash table entries: 1024 (order: 3, 32768 bytes, linear)
[    0.448087] NET: Registered PF_UNIX/PF_LOCAL protocol family
[    0.448447] RPC: Registered named UNIX socket transport module.
[    0.448456] RPC: Registered udp transport module.
[    0.448462] RPC: Registered tcp transport module.
[    0.448467] RPC: Registered tcp-with-tls transport module.
[    0.448472] RPC: Registered tcp NFSv4.1 backchannel transport module.
[    0.448485] PCI: CLS 0 bytes, default 64
[    0.448781] Trying to unpack rootfs image as initramfs...
[    0.453975] kvm [1]: nv: 554 coarse grained trap handlers
[    0.454287] kvm [1]: IPA Size Limit: 44 bits
[    0.454894] kvm [1]: vgic interrupt IRQ9
[    0.454990] kvm [1]: Hyp nVHE mode initialized successfully
[    0.456068] Initialise system trusted keyrings
[    0.456314] workingset: timestamp_bits=42 max_order=19 bucket_order=0
[    0.456740] NFS: Registering the id_resolver key type
[    0.456769] Key type id_resolver registered
[    0.456774] Key type id_legacy registered
[    0.456793] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
[    0.456802] nfs4flexfilelayout_init: NFSv4 Flexfile Layout Driver Registering                                                                                                             ...
[    0.457204] Key type asymmetric registered
[    0.457232] Asymmetric key parser 'x509' registered
[    0.457284] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 2                                                                                                             47)
[    0.457458] io scheduler mq-deadline registered
[    0.457468] io scheduler kyber registered
[    0.457494] io scheduler bfq registered
[    0.458024] irq_brcmstb_l2: registered L2 intc (/soc/interrupt-controller@7ef                                                                                                             00100, parent irq: 23)
[    0.459707] pinctrl-bcm2835 fe200000.gpio: GPIO_OUT persistence: yes
[    0.576148] Freeing initrd memory: 6772K
[    0.579461] ledtrig-cpu: registered to indicate activity on CPUs
[    0.580980] brcm-pcie fd500000.pcie: host bridge /scb/pcie@7d500000 ranges:
[    0.581023] brcm-pcie fd500000.pcie:   No bus range found for /scb/pcie@7d500                                                                                                             000, using [bus 00-ff]
[    0.581045] brcm-pcie fd500000.pcie:      MEM 0x0600000000..0x063fffffff -> 0                                                                                                             x00c0000000
[    0.581063] brcm-pcie fd500000.pcie:   IB MEM 0x0000000000..0x007fffffff -> 0                                                                                                             x0400000000
[    0.582363] brcm-pcie fd500000.pcie: PCI host bridge to bus 0000:00
[    0.582414] pci_bus 0000:00: root bus resource [bus 00-ff]
[    0.582425] pci_bus 0000:00: root bus resource [mem 0x600000000-0x63fffffff]                                                                                                              (bus address [0xc0000000-0xffffffff])
[    0.582485] pci 0000:00:00.0: [14e4:2711] type 01 class 0x060400 PCIe Root Po                                                                                                             rt
[    0.582503] pci 0000:00:00.0: PCI bridge to [bus 00]
[    0.582514] pci 0000:00:00.0:   bridge window [mem 0x80000000-0xbfffffff]
[    0.582565] pci 0000:00:00.0: PME# supported from D0 D3hot
[    0.584187] pci 0000:00:00.0: bridge configuration invalid ([bus 00-00]), rec                                                                                                             onfiguring
[    0.584320] pci_bus 0000:01: supply vpcie3v3 not found, using dummy regulator
[    0.584398] pci_bus 0000:01: supply vpcie3v3aux not found, using dummy regula                                                                                                             tor
[    0.584423] pci_bus 0000:01: supply vpcie12v not found, using dummy regulator
[    0.686930] brcm-pcie fd500000.pcie: clkreq-mode set to default
[    0.689000] brcm-pcie fd500000.pcie: link up, 5.0 GT/s PCIe x1 (SSC)
[    0.689123] pci 0000:01:00.0: [1106:3483] type 00 class 0x0c0330 PCIe Endpoin                                                                                                             t
[    0.689179] pci 0000:01:00.0: BAR 0 [mem 0x00000000-0x00000fff 64bit]
[    0.689270] pci 0000:01:00.0: ASPM: VL805 fixup applied
[    0.689356] pci 0000:01:00.0: PME# supported from D0 D3hot
[    0.694976] pci_bus 0000:01: busn_res: [bus 01-ff] end is updated to 01
[    0.695000] pci 0000:00:00.0: bridge window [mem 0x600000000-0x6000fffff]: as                                                                                                             signed
[    0.695011] pci 0000:01:00.0: BAR 0 [mem 0x600000000-0x600000fff 64bit]: assi                                                                                                             gned
[    0.695057] pci 0000:00:00.0: PCI bridge to [bus 01]
[    0.695065] pci 0000:00:00.0:   bridge window [mem 0x600000000-0x6000fffff]
[    0.695075] pci_bus 0000:00: resource 4 [mem 0x600000000-0x63fffffff]
[    0.695082] pci_bus 0000:01: resource 1 [mem 0x600000000-0x6000fffff]
[    0.695220] pcieport 0000:00:00.0: enabling device (0000 -> 0002)
[    0.695295] pcieport 0000:00:00.0: PME: Signaling with IRQ 27
[    0.695465] pcieport 0000:00:00.0: AER: enabled with IRQ 27
[    0.699278] Serial: 8250/16550 driver, 1 ports, IRQ sharing enabled
[    0.700107] iproc-rng200 fe104000.rng: hwrng registered
[    0.700193] vc-mem: phys_addr:0x00000000 mem_base=0x3ec00000 mem_size:0x40000                                                                                                             000(1024 MiB)
[    0.704252] brd: module loaded
[    0.706613] loop: module loaded
[    0.707020] Loading iSCSI transport class v2.0-870.
[    0.708813] bcmgenet fd580000.ethernet: GENET 5.0 EPHY: 0x0000
[    0.902954] unimac-mdio unimac-mdio.-19: Broadcom UniMAC MDIO bus
[    0.903475] usbcore: registered new interface driver lan78xx
[    0.903500] usbcore: registered new interface driver smsc95xx
[    0.994764] xhci_hcd 0000:01:00.0: xHCI Host Controller
[    0.994782] xhci_hcd 0000:01:00.0: new USB bus registered, assigned bus numbe                                                                                                             r 1
[    0.995638] xhci_hcd 0000:01:00.0: hcc params 0x002841eb hci version 0x100 qu                                                                                                             irks 0x0300240000000890
[    0.996088] xhci_hcd 0000:01:00.0: xHCI Host Controller
[    0.996099] xhci_hcd 0000:01:00.0: new USB bus registered, assigned bus numbe                                                                                                             r 2
[    0.996110] xhci_hcd 0000:01:00.0: Host supports USB 3.0 SuperSpeed
[    0.996236] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bc                                                                                                             dDevice= 6.12
[    0.996247] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=                                                                                                             1
[    0.996255] usb usb1: Product: xHCI Host Controller
[    0.996261] usb usb1: Manufacturer: Linux 6.12.34+rpt-rpi-v8 xhci-hcd
[    0.996267] usb usb1: SerialNumber: 0000:01:00.0
[    0.996507] hub 1-0:1.0: USB hub found
[    0.996529] hub 1-0:1.0: 1 port detected
[    0.996738] usb usb2: New USB device found, idVendor=1d6b, idProduct=0003, bc                                                                                                             dDevice= 6.12
[    0.996749] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=                                                                                                             1
[    0.996756] usb usb2: Product: xHCI Host Controller
[    0.996763] usb usb2: Manufacturer: Linux 6.12.34+rpt-rpi-v8 xhci-hcd
[    0.996769] usb usb2: SerialNumber: 0000:01:00.0
[    0.996935] hub 2-0:1.0: USB hub found
[    0.996955] hub 2-0:1.0: 4 ports detected
[    0.997340] dwc_otg: version 3.00a 10-AUG-2012 (platform bus)
[    0.997881] usbcore: registered new interface driver uas
[    0.997926] usbcore: registered new interface driver usb-storage
[    0.998145] mousedev: PS/2 mouse device common for all mice
[    0.999610] sdhci: Secure Digital Host Controller Interface driver
[    0.999630] sdhci: Copyright(c) Pierre Ossman
[    0.999716] sdhci-pltfm: SDHCI platform and OF driver helper
[    0.999876] hid: raw HID events driver (C) Jiri Kosina
[    0.999935] usbcore: registered new interface driver usbhid
[    0.999942] usbhid: USB HID core driver
[    1.004016] hw perfevents: enabled with armv8_cortex_a72 PMU driver, 7 (0,800                                                                                                             0003f) counters available
[    1.004588] NET: Registered PF_PACKET protocol family
[    1.004633] Key type dns_resolver registered
[    1.014083] registered taskstats version 1
[    1.014230] Loading compiled-in X.509 certificates
[    1.017696] Demotion targets for Node 0: null
[    1.018201] Key type .fscrypt registered
[    1.018210] Key type fscrypt-provisioning registered
[    1.021688] uart-pl011 fe201000.serial: there is not valid maps for state def                                                                                                             ault
[    1.021958] uart-pl011 fe201000.serial: cts_event_workaround enabled
[    1.022127] fe201000.serial: ttyAMA1 at MMIO 0xfe201000 (irq = 39, base_baud                                                                                                              = 0) is a PL011 rev3
[    1.022239] serial serial0: tty port ttyAMA1 registered
[    1.022890] bcm2835-aux-uart fe215040.serial: there is not valid maps for sta                                                                                                             te default
[    1.023300] printk: legacy console [ttyS0] disabled
[    1.023499] fe215040.serial: ttyS0 at MMIO 0xfe215040 (irq = 40, base_baud =                                                                                                              62500000) is a 16550
[    1.023532] printk: legacy console [ttyS0] enabled
[    2.642221] bcm2835-wdt bcm2835-wdt: Broadcom BCM2835 watchdog timer
[    2.648994] bcm2835-power bcm2835-power: Broadcom BCM2835 power domains drive                                                                                                             r
[    2.656908] mmc-bcm2835 fe300000.mmcnr: mmc_debug:0 mmc_debug2:0
[    2.663026] mmc-bcm2835 fe300000.mmcnr: DMA channel allocated
[    2.694943] of_cfs_init
[    2.697681] of_cfs_init: OK
[    2.700754] clk: Disabling unused clocks
[    2.704967] PM: genpd: Disabling unused power domains
[    2.734943] mmc0: SDHCI controller on fe340000.mmc [fe340000.mmc] using ADMA
[    2.747068] Freeing unused kernel memory: 5440K
[    2.751801] Run /init as init process
[    2.758970] usb 1-1: new high-speed USB device number 2 using xhci_hcd
[    2.800595] mmc1: new high speed SDIO card at address 0001
[    2.846440] mmc0: new ultra high speed DDR50 SDXC card at address aaaa
[    2.854547] mmcblk0: mmc0:aaaa SD64G 59.5 GiB
[    2.862049]  mmcblk0: p1 p2
[    2.867057] mmcblk0: mmc0:aaaa SD64G 59.5 GiB (quirks 0x00004000)
[    2.905584] usb 1-1: New USB device found, idVendor=2109, idProduct=3431, bcd                                                                                                             Device= 4.21
[    2.914009] usb 1-1: New USB device strings: Mfr=0, Product=1, SerialNumber=0
[    2.921301] usb 1-1: Product: USB2.0 Hub
[    2.935421] hub 1-1:1.0: USB hub found
[    2.939662] hub 1-1:1.0: 4 ports detected
[    2.951591] bcmgenet fd580000.ethernet end0: renamed from eth0
[    3.432862] EXT4-fs (mmcblk0p2): mounted filesystem ce208fd3-38a8-424a-87a2-c                                                                                                             d44114eb820 ro with ordered data mode. Quota mode: none.
[    3.893221] systemd[1]: System time before build time, advancing clock.
[    4.002821] NET: Registered PF_INET6 protocol family
[    4.008556] Segment Routing with IPv6
[    4.012306] In-situ OAM (IOAM) with IPv6
[    4.053255] systemd[1]: systemd 252.38-1~deb12u1 running in system mode (+PAM                                                                                                              +AUDIT +SELINUX +APPARMOR +IMA +SMACK +SECCOMP +GCRYPT -GNUTLS +OPENSSL +ACL +B                                                                                                             LKID +CURL +ELFUTILS +FIDO2 +IDN2 -IDN +IPTC +KMOD +LIBCRYPTSETUP +LIBFDISK +PCR                                                                                                             E2 -PWQUALITY +P11KIT +QRENCODE +TPM2 +BZIP2 +LZ4 +XZ +ZLIB +ZSTD -BPF_FRAMEWORK                                                                                                              -XKBCOMMON +UTMP +SYSVINIT default-hierarchy=unified)
[    4.086476] systemd[1]: Detected architecture arm64.
[    4.102956] systemd[1]: Hostname set to <raspberrypi>.
[    4.548287] systemd[1]: Queued start job for default target multi-user.target                                                                                                             .
[    4.584096] systemd[1]: Created slice system-getty.slice - Slice /system/gett                                                                                                             y.
[    4.592319] systemd[1]: Created slice system-modprobe.slice - Slice /system/m                                                                                                             odprobe.
[    4.600872] systemd[1]: Created slice system-serial\x2dgetty.slice - Slice /s                                                                                                             ystem/serial-getty.
[    4.610368] systemd[1]: Created slice system-systemd\x2dfsck.slice - Slice /s                                                                                                             ystem/systemd-fsck.
[    4.619702] systemd[1]: Created slice user.slice - User and Session Slice.
[    4.626903] systemd[1]: Started systemd-ask-password-console.path - Dispatch                                                                                                              Password Requests to Console Directory Watch.
[    4.638298] systemd[1]: Started systemd-ask-password-wall.path - Forward Pass                                                                                                             word Requests to Wall Directory Watch.
[    4.649288] systemd[1]: Set up automount proc-sys-fs-binfmt_misc.automount -                                                                                                              Arbitrary Executable File Formats File System Automount Point.
[    4.662141] systemd[1]: Expecting device dev-disk-by\x2dpartuuid-17e43e1f\x2d                                                                                                             01.device - /dev/disk/by-partuuid/17e43e1f-01...
[    4.673728] systemd[1]: Expecting device dev-ttyS0.device - /dev/ttyS0...
[    4.680714] systemd[1]: Reached target cryptsetup.target - Local Encrypted Vo                                                                                                             lumes.
[    4.688593] systemd[1]: Reached target integritysetup.target - Local Integrit                                                                                                             y Protected Volumes.
[    4.697739] systemd[1]: Reached target paths.target - Path Units.
[    4.704047] systemd[1]: Reached target slices.target - Slice Units.
[    4.710510] systemd[1]: Reached target swap.target - Swaps.
[    4.716270] systemd[1]: Reached target veritysetup.target - Local Verity Prot                                                                                                             ected Volumes.
[    4.725107] systemd[1]: Listening on systemd-fsckd.socket - fsck to fsckd com                                                                                                             munication Socket.
[    4.734148] systemd[1]: Listening on systemd-initctl.socket - initctl Compati                                                                                                             bility Named Pipe.
[    4.743565] systemd[1]: Listening on systemd-journald-audit.socket - Journal                                                                                                              Audit Socket.
[    4.752314] systemd[1]: Listening on systemd-journald-dev-log.socket - Journa                                                                                                             l Socket (/dev/log).
[    4.761666] systemd[1]: Listening on systemd-journald.socket - Journal Socket                                                                                                             .
[    4.769906] systemd[1]: Listening on systemd-udevd-control.socket - udev Cont                                                                                                             rol Socket.
[    4.778420] systemd[1]: Listening on systemd-udevd-kernel.socket - udev Kerne                                                                                                             l Socket.
[    4.786827] systemd[1]: dev-hugepages.mount - Huge Pages File System was skip                                                                                                             ped because of an unmet condition check (ConditionPathExists=/sys/kernel/mm/huge                                                                                                             pages).
[    4.843127] systemd[1]: Mounting dev-mqueue.mount - POSIX Message Queue File                                                                                                              System...
[    4.853065] systemd[1]: Mounting sys-kernel-debug.mount - Kernel Debug File S                                                                                                             ystem...
[    4.862966] systemd[1]: Mounting sys-kernel-tracing.mount - Kernel Trace File                                                                                                              System...
[    4.871486] systemd[1]: auth-rpcgss-module.service - Kernel Module supporting                                                                                                              RPCSEC_GSS was skipped because of an unmet condition check (ConditionPathExists                                                                                                             =/etc/krb5.keytab).
[    4.890098] systemd[1]: Starting fake-hwclock.service - Restore / save the cu                                                                                                             rrent clock...
[    4.902252] systemd[1]: Starting keyboard-setup.service - Set the console key                                                                                                             board layout...
[    4.913320] systemd[1]: Starting kmod-static-nodes.service - Create List of S                                                                                                             tatic Device Nodes...
[    4.924890] systemd[1]: Starting modprobe@configfs.service - Load Kernel Modu                                                                                                             le configfs...
[    4.936142] systemd[1]: Starting modprobe@dm_mod.service - Load Kernel Module                                                                                                              dm_mod...
[    4.946970] systemd[1]: Starting modprobe@drm.service - Load Kernel Module dr                                                                                                             m...
[    4.957882] systemd[1]: Starting modprobe@efi_pstore.service - Load Kernel Mo                                                                                                             dule efi_pstore...
[    4.968066] device-mapper: ioctl: 4.48.0-ioctl (2023-03-01) initialised: dm-d                                                                                                             evel@lists.linux.dev
[    4.969308] systemd[1]: Starting modprobe@fuse.service - Load Kernel Module f                                                                                                             use...
[    4.988836] systemd[1]: Starting modprobe@loop.service - Load Kernel Module l                                                                                                             oop...
[    4.997156] systemd[1]: systemd-fsck-root.service - File System Check on Root                                                                                                              Device was skipped because of an unmet condition check (ConditionPathExists=!/r                                                                                                             un/initramfs/fsck-root).
[    5.015688] fuse: init (API version 7.41)
[    5.022048] systemd[1]: Starting systemd-journald.service - Journal Service..                                                                                                             .
[    5.033355] systemd[1]: Starting systemd-modules-load.service - Load Kernel M                                                                                                             odules...
[    5.044335] systemd[1]: Starting systemd-remount-fs.service - Remount Root an                                                                                                             d Kernel File Systems...
[    5.056345] systemd[1]: Starting systemd-udev-trigger.service - Coldplug All                                                                                                              udev Devices...
[    5.068834] systemd[1]: Mounted dev-mqueue.mount - POSIX Message Queue File S                                                                                                             ystem.
[    5.077216] i2c_dev: i2c /dev entries driver
[    5.082773] systemd[1]: Mounted sys-kernel-debug.mount - Kernel Debug File Sy                                                                                                             stem.
[    5.092165] systemd[1]: Mounted sys-kernel-tracing.mount - Kernel Trace File                                                                                                              System.
[    5.100839] systemd[1]: Finished fake-hwclock.service - Restore / save the cu                                                                                                             rrent clock.
[    5.111872] systemd[1]: Finished keyboard-setup.service - Set the console key                                                                                                             board layout.
[    5.123100] systemd[1]: Finished kmod-static-nodes.service - Create List of S                                                                                                             tatic Device Nodes.
[    5.123170] EXT4-fs (mmcblk0p2): re-mounted ce208fd3-38a8-424a-87a2-cd44114eb                                                                                                             820 r/w.
[    5.144684] systemd[1]: Started systemd-journald.service - Journal Service.
[    5.224055] systemd-journald[253]: Received client request to flush runtime j                                                                                                             ournal.
[    5.245306] systemd-journald[253]: File /var/log/journal/936c7c99213d4805a9d2                                                                                                             bd65211ddd14/system.journal corrupted or uncleanly shut down, renaming and repla                                                                                                             cing.

Debian GNU/Linux 12 raspberrypi ttyS0

My IP address is 127.0.1.1 ::ffff:127.0.1.1

raspberrypi login:
Debian GNU/Linux 12 raspberrypi ttyS0

My IP address is 10.196.214.234 fe80::21b8:4155:c476:513

raspberrypi login
```
