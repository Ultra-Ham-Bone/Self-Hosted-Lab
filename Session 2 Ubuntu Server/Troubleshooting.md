# Troubleshooting Log

---

## Session 2 - Linux Server and SSH

### VM boots into installer upon Ubuntu installation

**When it happened**
After Ubuntu Server installation completed and the VM restarted again instead of booting into the installed system.

**Cause**
The Ubuntu Server ISO was still attached to the VM virtuall optical drive.

##How I fixed it**
1. Shut down the VM (Machine > Close > Power off)
2. Go to VM Settings > Storage
3. Click the optical drive
4. Click the small icon and select remove disk from Virtual Drive
5. Start the VM again

The VM booted correctly in the installed Ubuntu Server

**How to prevent it**
During Ubuntu Server installation final steps, remove the ISO from virtual optical drive

**Lesson**
Always check thte virtual drive in Settings after a fresh installation
