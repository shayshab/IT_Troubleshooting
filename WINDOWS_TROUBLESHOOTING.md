# Windows Troubleshooting Guide

Senior runbook with evidence-driven steps and commands.

## Performance & Startup

| Symptom | Actions |
|---------|---------|
| Slow system | Task Manager: sort by CPU/Disk/Memory. Check Startup apps; disable nonessential. Run `sfc /scannow`, then `DISM /Online /Cleanup-Image /RestoreHealth`. Check disk space and `chkdsk /scan`. Update drivers/Windows. |
| Hangs/BSOD | Review Event Viewer → System/Application, and `C:\Windows\Minidump`. Update chipset/GPU/NIC drivers. Test RAM with Windows Memory Diagnostic. |

## Network

| Symptom | Actions |
|---------|---------|
| No/limited connectivity | `ipconfig /all`, `ipconfig /release` + `/renew`. Reset stack: `netsh int ip reset`, `netsh winsock reset`. Test `ping 8.8.8.8` and `nslookup microsoft.com`. Check VPN/adapters priority. |
| Wi‑Fi issues | Forget/rejoin SSID, update Wi‑Fi driver. `netsh wlan show interfaces` for RSSI/SNR. |

## Login & Account

| Symptom | Actions |
|---------|---------|
| Can't sign in | Verify password/SSO, network at login screen. For Azure AD: check device join state `dsregcmd /status`. For domain: `nltest /dsgetdc:domain`. |

## Apps & Services

| Symptom | Actions |
|---------|---------|
| App crashes | Event Viewer → Application. Repair/reset via Settings → Apps. Reinstall with latest VC++ runtimes. |
| Printing issues | Restart spooler: `net stop spooler && net start spooler`. Reinstall printer and drivers. |

## Updates & Security

| Symptom | Actions |
|---------|---------|
| Windows Update fails | `services.msc`: restart BITS and Windows Update. Clear cache: stop services, delete `C:\Windows\SoftwareDistribution\Download`, start services. Run Windows Update Troubleshooter. |
| Defender/AV | `Get-MpComputerStatus` (PowerShell). Update signatures and run Quick Scan. |

## Disk & Files

| Symptom | Actions |
|---------|---------|
| Low space | Storage Sense, `WinDirStat`/`du` for large folders. Clear temp `%TEMP%`. Move OneDrive cache if needed. |
| File access/permissions | Check ownership and ACLs. `icacls` to reset. |

## Evidence Collection

- Note timestamp and error text. Export Event Viewer logs. Collect DxDiag and `msinfo32` NFO for hardware state.

