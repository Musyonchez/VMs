# Windows VM Setup Progress

## Goal
Set up Windows 10 VM to run Aquile Reader for reading epub novels.

## Completed ✅
1. **QEMU/KVM Installation** - Installed full virtualization stack
2. **Libvirt Service** - Enabled and configured
3. **Windows 10 ISO** - Downloaded to ~/Downloads

## Next Steps (After Login) 🔄
1. **Logout/Login** - Required for libvirt group permissions to take effect
2. **Launch virt-manager**: `virt-manager`
3. **Create VM** with these settings:
   - **Source**: Local install media (ISO image)
   - **ISO Path**: ~/Downloads/Win10_22H2_English_x64.iso
   - **OS Type**: Windows 10
   - **Memory**: 4-6GB RAM
   - **CPUs**: 2-4 cores
   - **Storage**: 60GB+ disk space
   - **Network**: NAT (default)
4. **Install Windows 10** - Follow installation wizard
5. **Install Aquile Reader** - Download and install in Windows VM

## System Specs
- CPU: Intel i5-4300U (4 cores, 1.9GHz) ✅ Compatible
- RAM: 15GB ✅ Sufficient
- Storage: 238GB ✅ Adequate
- Virtualization: KVM supported ✅

## Commands Reference
```bash
# Launch VM manager
virt-manager

# Check VM status
virsh list --all

# Start VM (if needed)
virsh start <vm-name>
```

## Notes
- Windows 10 chosen over 11 (better compatibility with older hardware)
- VM will use ~4-6GB RAM, leaving 9-11GB for host system
- Performance should be good for reading applications