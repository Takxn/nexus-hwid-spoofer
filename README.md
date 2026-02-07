# Nexus+ HWID Spoofer v3.1.3

<p align="center">
  <img src="logo.png" alt="Nexus+" width="120">
</p>

<p align="center">
  <b>Premium Hardware ID Spoofing Solution with Kernel-Level Driver</b>
</p>

---

## Features

| Component | Kernel-Level | Registry | IRP Hook | Coverage |
|-----------|:----------:|:--------:|:--------:|----------|
| Disk Serial | Yes | Yes | Yes | Full - 3 layers of protection |
| MAC Address | Yes | Yes (NDIS) | - | Full - Driver + Registry |
| Machine GUID | - | Yes | - | Full |
| Product ID | - | Yes | - | Full |
| Board Serial | - | Yes (5 keys) | - | Full |
| BIOS Serial | - | Yes (4 keys) | - | Full |
| GPU Serial | Dedicated GPU | Yes (11x WMI/PNP) | - | Full (Registry for iGPU) |
| SMBIOS Tables | - | Yes (all keys) | - | Full |
| Telemetry/SQM | - | Cleared | - | Full |
| DNS Cache | - | Flushed | - | Full |
| Install Date | - | Changed | - | Full |
| EFI Variables | - | Cleared | - | Full |

> **Note:** Kernel-level GPU spoofing works with dedicated NVIDIA/AMD GPUs. Intel iGPUs are fully spoofed via Registry/WMI.

---

## What's New in v3.1.3

- **Kernel Driver v16.3** - Safe, crash-free kernel-level spoofing
- **IRP Hook System** - Intercepts ALL storage IOCTLs (STORAGE_QUERY_PROPERTY, ATA_PASS_THROUGH, SMART, SCSI)
- **Device Extension Patching** - Direct memory manipulation of Disk and NIC driver data
- **Exact MAC Matching** - Finds and replaces your real MAC address in kernel memory
- **IOCTL Communication** - App communicates directly with kernel driver for real-time spoofing
- **Safe Memory Access** - No MmProbeAndLockPages, no BSODs
- **NDIS Registry Spoofing** - Patches network adapter config at driver level
- **Full SMBIOS Registry Coverage** - All motherboard, BIOS, system, chassis keys
- **Two-Phase Workflow** - Original values displayed, then spoofed on command
- **Logout Feature** - Account management from profile dropdown
- **Auto Path Detection** - Correct driver paths for both dev and installed versions

---

## Anti-Cheat Compatibility

### Tested & Working

| Anti-Cheat | Compatibility | Details |
|------------|:------------:|---------|
| BattlEye (BE) | Excellent | IRP Hooks intercept all disk queries, full registry coverage |
| EasyAntiCheat (EAC) | Very Good | Kernel disk spoofing + registry + IRP hooks |
| FACEIT AC | Excellent | Registry-based detection fully covered |
| ESEA AC | Excellent | Registry-based detection fully covered |
| Ricochet (CoD) | Good | Registry + IRP hooks cover most checks |

### Game Compatibility

| Game | Anti-Cheat | Status |
|------|-----------|--------|
| Fortnite | EAC | Working |
| Apex Legends | EAC | Working |
| PUBG | BattlEye | Working |
| Rust | EAC | Working |
| Escape from Tarkov | BattlEye | Working |
| Rainbow Six Siege | BattlEye | Working |
| Arma 3 / Reforger | BattlEye | Working |
| DayZ | BattlEye | Working |
| Call of Duty (Warzone/MW3) | Ricochet | Working |
| CS2 (FACEIT/ESEA) | FACEIT/ESEA | Working |
| FiveM | Custom AC | Working |
| The Finals | EAC | Working |
| Dead by Daylight | EAC | Working |

### Not Recommended

| Anti-Cheat | Reason |
|------------|--------|
| Vanguard (Valorant) | Ring 0 kernel driver with physical memory scanning - too aggressive |

---

## How It Works

```
1. Driver loads as Windows Service (Test Signing)
2. IRP Hooks installed on \Driver\Disk
3. App sends spoof values via IOCTL to kernel driver
4. Kernel driver patches:
   - Disk device extensions (direct memory)
   - NIC device extensions (exact MAC replacement)
   - Registry (GUID, Board, BIOS, SMBIOS, GPU, Telemetry)
   - NDIS adapter configuration
5. IRP Hooks intercept all future storage queries
   -> Anti-cheat reads spoofed serial instead of real one
```

---

## Pricing

| Duration | Price |
|----------|-------|
| 1 Day | 3 EUR |
| 1 Week | 7 EUR |
| 1 Month | 20 EUR |

Payment via PayPal (Apple Pay, Visa, Mastercard supported).

---

## System Requirements

- Windows 10/11 (64-bit)
- Administrator privileges
- Secure Boot **disabled**
- Test Signing Mode **enabled**
- Discord account (for license activation)

---

## Setup Guide (MUST DO before spoofing!)

Follow these steps **in order** before using the spoofer. Skipping steps will cause the spoofer to fail or get detected.

### Step 1: Disable Secure Boot

1. Restart your PC
2. Enter BIOS/UEFI (press **F2**, **Del**, or **F12** during boot - depends on your motherboard)
3. Navigate to **Security** or **Boot** tab
4. Set **Secure Boot** to **Disabled**
5. Save & Exit (usually **F10**)

### Step 2: Test Signing Mode (automatic)

Nexus+ **automatically enables** Test Signing Mode when you click SPOOF for the first time. You just need to **restart your PC** when prompted. After the restart, spoofing will work automatically.

> **Note:** You may see a "Test Mode" watermark on your desktop. This is normal. You can remove it with "Universal Watermark Disabler" without affecting spoofing.

### Step 3: Disable Windows Defender / Antivirus

Windows Defender can block the kernel driver. You must disable it:

1. Open **Windows Security** > **Virus & threat protection**
2. Click **Manage settings** under "Virus & threat protection settings"
3. Turn **OFF**:
   - Real-time protection
   - Cloud-delivered protection
   - Automatic sample submission
   - Tamper protection (turn off FIRST if other toggles are greyed out)

**Alternative:** Use **dControl** (included in Nexus+ tools folder) to fully disable Defender with one click.

### Step 4: Disable Memory Integrity (HVCI)

1. Open **Windows Security** > **Device security**
2. Click **Core isolation details**
3. Turn **OFF** Memory integrity
4. Restart your PC

### Step 5: Close all Games & Anti-Cheats

Before spoofing, make sure the following are **completely closed** (check Task Manager):

- BattlEye Service (`BEService.exe`)
- EasyAntiCheat (`EasyAntiCheat.exe`)
- Vanguard (`vgc.exe`, `vgtray.exe`)
- FACEIT AC (`faceitclient.exe`)
- Any game that uses these anti-cheats

### Step 6: Run Nexus+ as Administrator

Always right-click `Nexus+.exe` and select **"Run as administrator"**. Without admin rights, the kernel driver cannot load.

---

## Quick Checklist

| Setting | Required State | How to Check |
|---------|---------------|-------------|
| Secure Boot | OFF | BIOS > Security |
| Test Signing | ON (auto-enabled) | Look for "Test Mode" watermark on desktop |
| Windows Defender | OFF | Windows Security > Real-time protection |
| Memory Integrity | OFF | Windows Security > Core isolation |
| Anti-Cheat | CLOSED | Task Manager > check for BEService, EAC |
| Run as Admin | YES | Right-click > Run as administrator |

---

## Installation

1. Download `Nexus+-Setup-3.1.3.exe`
2. Run as Administrator
3. Follow the installation wizard
4. **Complete all 6 setup steps above first!**
5. Launch Nexus+ from Desktop
6. Login with Discord
7. Activate your license key
8. Click "SPOOF" - original values shown, then spoofed
9. Restart PC for full effect

---

## Important Notes

```
This spoofer provides NO 100% guarantee for unbanning.
Success rate depends on:

- Your hardware configuration
- Anti-cheat version and update state
- Type of ban (HWID, IP, Account)
- Windows version and updates
- Whether you have a dedicated or integrated GPU

Use at your own risk.
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Driver not loading | Enable Test Signing: `bcdedit /set testsigning on` + reboot |
| Mapping failed | Restart PC, then try again |
| BSOD | Update to latest version (v3.1.3 has safe memory access) |
| Spoof failed | Run as Administrator |
| Login issues | Check Discord connection, try "Switch Account" |
| GPU not kernel-spoofed | Normal for Intel iGPU - GPU is still registry-spoofed |

---

## Support

- [Discord Server](https://discord.gg/nexus-plus)
- Support available after purchase

---

## Changelog

### v3.1.3 (February 2026)
- Kernel Driver v16.3 with safe memory access (no BSODs)
- Active device extension patching for Disk and NIC
- IRP Hook completion routines for storage IOCTLs
- IOCTL communication between app and kernel driver
- Exact MAC matching in kernel memory
- NDIS registry spoofing for network adapters
- Full SMBIOS registry coverage
- Improved anti-cheat bypass for BattlEye and EAC

### v3.1.2 (February 2026)
- Fixed driver path detection for installed version
- Fixed service loading with Test Signing
- KDMapper fallback improvements
- Logout feature added
- UI text updates after successful spoof

### v3.1.1 (January 2026)
- Side-by-side original/spoofed value display
- Kernel status indicator
- Version display updates

### v3.0.0 (January 2026)
- Initial release with kernel driver
- Basic HWID spoofing functionality
- Discord integration

---

<p align="center">
  <b>&copy; 2026 Nexus+ | All Rights Reserved</b>
</p>

<img width="1800" height="1300" alt="image" src="https://github.com/user-attachments/assets/972705b4-7d90-4e1b-84fd-cef6f669fdb5" />
