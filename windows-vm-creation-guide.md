# Complete Windows 10 VM Setup Guide

## Prerequisites
- QEMU/KVM installed and configured
- Libvirt service enabled
- User added to libvirt group (requires logout/login)
- Windows 10 ISO file downloaded

## Step 1: Launch Virtual Machine Manager
```bash
virt-manager
```

## Step 2: Create New Virtual Machine
1. Click **"Create a new virtual machine"** (computer icon with plus)
2. Select **"Local install media (ISO image or CDROM)"**
3. Click **"Forward"**

## Step 3: Choose Installation Media
1. Click **"Browse"**
2. Navigate to your Windows 10 ISO file location
3. Select the ISO file and click **"Choose Volume"**
4. OS should auto-detect as **"Microsoft Windows 10"**
5. Click **"Forward"**

## Step 4: Set Memory and CPU
1. **Memory**: 4096 MB (4GB) or 6144 MB (6GB)
2. **CPUs**: 2 or 4 cores
3. Click **"Forward"**

## Step 5: Configure Storage
1. **Create disk image**: 60 GB or more
2. Click **"Forward"**

## Step 6: Final VM Settings
1. **Name**: Choose a descriptive name (e.g., "Windows10-AquileReader")
2. **Network**: Leave as default (NAT)
3. Click **"Finish"**

## Step 7: Boot and Install Windows

### Boot Selection
- VM will start and show boot options
- Choose **"QEMU DVD-ROM"** option to boot from ISO

### Windows Installation Process

#### 7.1 Initial Setup
1. Wait for Windows loading screen with spinning dots
2. Select language, time, and keyboard settings
3. Click **"Next"**
4. Click **"Install now"**

#### 7.2 Product Key
- Choose **"I don't have a product key"** (for 30-day trial)
- Or enter valid product key if available

#### 7.3 Windows Edition
- Select **"Windows 10 Home"**
- Click **"Next"**

#### 7.4 Installation Type
- Select **"Custom: Install Windows only (advanced)"**
- Click **"Next"**

#### 7.5 Disk Setup
1. Select the **unallocated space** (your virtual hard drive)
2. Click **"Next"**
3. Windows will automatically partition and begin installation

## Step 8: Complete Installation
1. Installation takes 10-20 minutes
2. VM will restart automatically
3. Follow Windows initial setup (user account, privacy settings, etc.)
4. Install any needed drivers or updates

## Step 9: Install Target Software
- Download and install Aquile Reader or other required applications
- Configure Windows as needed

## Useful Commands Reference
```bash
# Launch VM manager
virt-manager

# Check VM status
virsh list --all

# Start VM (if needed)
virsh start <vm-name>

# Stop VM
virsh shutdown <vm-name>

# Force stop VM
virsh destroy <vm-name>
```

## System Recommendations
- **RAM allocation**: 4-6GB (leave 9-11GB for host)
- **CPU cores**: 2-4 (depending on host CPU)
- **Storage**: 60GB+ for Windows + applications
- **Network**: NAT (default) works for most use cases

## Troubleshooting
- If VM doesn't boot: Check virtualization is enabled in BIOS
- If ISO doesn't load: Verify ISO file path and permissions
- If performance is slow: Adjust RAM/CPU allocation or enable hardware acceleration

## Notes
- Windows 10 chosen for better compatibility with older hardware
- Unactivated Windows runs fully functional for 30 days
- VM can be paused/resumed as needed to save system resources