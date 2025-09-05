# Printer Troubleshooting Guide

Senior checklist with device, driver, queue, and network layers.

## Discovery

- Model and connection type (USB/Ethernet/Wi‑Fi/AirPrint).
- Status page/print: get IP address and consumables level.
- OS print subsystem health; collect timestamps and error text.

## Common Issues and Actions

| Issue | Actions |
|------|---------|
| Not detected | For USB: try alternate cable/port; check System Report → USB. For network: ping printer IP; verify same subnet/VLAN; print config page from device. |
| Not printing | Clear user and system queues. On macOS: System Settings → Printers & Scanners; remove/re‑add. For CUPS: `http://localhost:631` enable web interface, cancel jobs, restart service. |
| Jobs stuck | Restart print system on macOS: System Settings → Printers & Scanners → right‑click any printer → Reset printing system. Or via Terminal: `sudo launchctl kickstart -kp system/org.cups.cupsd`. |
| Poor quality | Run built‑in cleaning/calibration. Check paper type/weight and settings. Replace low toner/ink; inspect drum/fuser life. |
| Paper jams | Remove all fragments, check rollers and tray guides. Inspect duplexer path. |
| Offline | Ensure static/reserved IP. Set as default printer. Wake from sleep; disable Deep Sleep where problematic. |
| Driver issues | Prefer vendor driver if features needed; otherwise AirPrint/IPP. Remove old drivers and reinstall. Verify architecture compatibility. |
| Cannot add | Ensure user has rights. On managed Macs, verify profiles and restrictions. Test with IPP/IPP‑Everywhere by IP address. |
| Wireless fails | Rejoin SSID on printer panel. Ensure 2.4 GHz if printer lacks 5 GHz. Reserve IP via DHCP. |
| Slow printing | Use draft quality for large docs. Check duplexing slowdown. Verify network path and switch errors. |
| Error codes | Look up vendor code; often fuser/transfer belt/sensor. Keep a quick table for your models. |
| Scanning broken | Update scanner driver or use Image Capture/AirScan. Test SMB/FTP destinations and permissions. |
| Duplex not working | Enable duplex in driver and app print dialog. Confirm hardware duplexer installed. |
| Color issues | Run color calibration. Replace specific color cartridge; verify ICC profiles if needed. |
| Sharing fails | Check macOS printer sharing and firewall rules. On networks, ensure Bonjour/mDNS across VLANs (use mDNS gateway if segmented). |

## Verification & Logging

- Print internal test page; then a PDF from the Mac.
- Save CUPS error log: `/var/log/cups/error_log` with `LogLevel debug` temporarily if needed.