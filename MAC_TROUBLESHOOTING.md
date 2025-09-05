# Mac Troubleshooting Guide

Use this senior-level runbook with evidence-led steps, commands, and verification. Always capture timestamps, error text, and screenshots.

## System Unresponsive / Performance

| Symptom | Actions |
|---------|---------|
| Spinning beach ball | Force quit problematic app. Open Activity Monitor → CPU/Memory; sort by highest. Collect sample for high CPU processes. Verify free disk: `df -h`. Check unified logs: `log show --style syslog --last 10m | grep -i "hang\|stall\|watchdog"`. Reboot if kernel_task is abnormally high; check sensors/fans and SMC reset if thermal. |
| Slow after login | Check Login Items (System Settings → General → Login Items). Create a fresh user to isolate profile. Safe Mode boot to disable third-party extensions. Check LaunchAgents/Daemons in `/Library/LaunchAgents`, `/Library/LaunchDaemons`, `~/Library/LaunchAgents`. |

## Power / Boot

| Symptom | Actions |
|---------|---------|
| Won't power on | Verify power, long-press power 10s. For Apple silicon: press and hold power until Options. For Intel: SMC reset; NVRAM reset (Option+Command+P+R). Test with known-good charger/cable. |
| Stuck on Apple logo | Safe Mode. Recovery (Command+R) → Disk Utility First Aid. Check available space (need >10GB). Reinstall macOS if system volume corrupted. Collect diagnostics: `sysdiagnose` (Shift+Ctrl+Option+Cmd+.) if possible. |

## Network

| Symptom | Actions |
|---------|---------|
| Wi‑Fi not connecting | Toggle Wi‑Fi. Forget/rejoin SSID. Renew DHCP lease. Delete Wi‑Fi service and re-add. Verify IP: `ipconfig getifaddr en0` and DNS: `scutil --dns`. Test reachability: `ping -c 4 8.8.8.8` then `ping -c 4 google.com`. Reset network: delete `/Library/Preferences/SystemConfiguration/com.apple.airport.preferences.plist` and reboot. |
| Frequent drops | Check environment (microwave, cordless phones). Lock channel/bandwidth on AP. Update macOS and Wi‑Fi firmware on AP. Capture logs: `log stream --predicate 'subsystem == "com.apple.network"' --info`. |
| VPN cannot connect | Validate creds and server. Inspect logs: app logs plus `log show --last 20m --predicate 'process == "neagent"'`. Flush DNS: `sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder`. |

## Peripherals

| Symptom | Actions |
|---------|---------|
| USB not recognized | Try different ports/cable. Check `About This Mac → System Report → USB`. Reset SMC (Intel). Inspect logs on connect: `log stream --predicate 'eventMessage CONTAINS[c] "USB"' --info`. |
| External display missing | Detect Displays. Check cable/adapters, try lower refresh rate. For USB‑C hubs, test direct. Reset NVRAM. Gather EDID via System Report. |
| Bluetooth issues | Toggle BT, remove/re‑pair devices. Reset BT module: remove `/Library/Preferences/com.apple.Bluetooth.plist` and reboot. |

## Audio / Video

| Symptom | Actions |
|---------|---------|
| No sound | Check Output device. Restart coreaudio: `sudo launchctl kickstart -kp system/com.apple.audio.coreaudiod`. Verify app permissions (Mic/Camera). |
| Camera not working | Quit all camera apps. `sudo killall VDCAssistant AppleCameraAssistant`. Test in FaceTime/Photo Booth. |

## Storage

| Symptom | Actions |
|---------|---------|
| Disk full | Storage Settings → Manage. Find large dirs: `sudo du -xh -d 1 / | sort -h | tail -n 20`. Clear caches cautiously in `~/Library/Caches`. Move archives to external/cloud. |
| Time Machine fails | Verify target disk. Exclude problematic paths. Check TM logs: `log show --predicate 'subsystem == "com.apple.TimeMachine"' --last 1h`. Reset TM and re-add destination. |

## Updates / System Integrity

| Symptom | Actions |
|---------|---------|
| Updates won't install | Ensure >15GB free. Safe Mode. `softwareupdate -l` then `sudo softwareupdate -ia`. Reset NVRAM if repeated failures. |
| Permissions / First Aid | Disk Utility → First Aid on all volumes. Repair Home folder ACLs if needed. |

## Crashes / Kernel Panics

| Symptom | Actions |
|---------|---------|
| Kernel panic | Collect panic logs: `/Library/Logs/DiagnosticReports`. Check third‑party kexts: `kmutil showloaded`. Remove problematic extensions, test Safe Mode. Run Apple Diagnostics (power on holding D). |

## Account & iCloud

| Symptom | Actions |
|---------|---------|
| iCloud sync issues | Sign out/in. Verify iCloud storage. Check `bird` logs: `log show --predicate 'process == "bird"' --last 30m`. |
| Login items causing problems | System Settings → Login Items. Disable all, add back gradually. Safe Mode to validate. |

## Reference Resets

- NVRAM/PRAM: restart and hold Option+Command+P+R for ~20s (Intel).
- SMC: Intel T2 laptops – shut down, hold Shift+Control+Option+Power for 10s; Apple silicon has no user SMC reset; use full shutdown.

## Evidence Collection

- Create sysdiagnose: press Shift+Control+Option+Command+Period, wait for completion in `/var/tmp/`.
- Note exact time of error for targeted `log show` queries.