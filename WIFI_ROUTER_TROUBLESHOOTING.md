# WiFi & Router Troubleshooting Guide

Senior workflow: validate WAN, LAN, RF, DHCP/DNS, and client config. Capture timestamps and topology.

## Quick Health Checks

- ISP/Modem: power, link lights, WAN IP present on router.
- Status page: router dashboard for errors, CPU/RAM, and logs.
- Scope: one device vs all; 2.4 GHz vs 5 GHz; SSID vs VLAN.

## Diagnostics

- WAN reachability: `ping -c 4 8.8.8.8` from router or a wired host.
- DNS resolution: `nslookup google.com` or `dig google.com`.
- DHCP: verify leases and conflicts; on client `ipconfig getpacket en0` (macOS).
- RF: check RSSI/SNR per client; move closer; test alternate channel/width.
- Throughput baseline: wired speed test vs Wi‑Fi to isolate RF vs ISP.

## Common Issues and Actions

| Issue | Actions |
|------|---------|
| No internet | Verify WAN link and IP. If PPPoE/vLAN required, confirm credentials and tagging. Reboot modem then router. Check ISP outage page. |
| Slow Wi‑Fi | Fix channel to 1/6/11 (2.4 GHz) or a clean 5 GHz channel; set 20/40 MHz width appropriately. Disable legacy rates if many retries. Update AP firmware. |
| Frequent disconnects | Check power save settings on clients. Ensure band steering and roaming thresholds are sane. Look for DFS events. Review router/AP logs for deauth/disassoc reasons. |
| Device can't join | Forget/rejoin. Check MAC filtering, WPA2/WPA3 mode compatibility. Ensure correct time on router for WPA3/802.1X. |
| IP conflicts | Shorten/expand DHCP scope; reserve static IPs outside scope. Clear rogue DHCP servers. |
| Router login issues | Confirm management IP, try wired. Reset password via vendor process. Backup config before factory reset. |
| Guest network fails | Verify VLAN isolation and DHCP on guest. Firewall rules allow DNS/DHCP but block LAN. |
| DNS issues | Use public DNS temporarily (8.8.8.8/1.1.1.1). Check conditional forwarders/split DNS if on corporate network. |
| Firmware update fails | Verify model/region and power stability. Update via wired connection. Factory reset only after config backup. |
| Port forwarding broken | Confirm WAN IP is public (no CGNAT). Verify NAT/UPnP and firewall rules. Test from external network. |

## Verification & Logging

- Post‑fix: test ping, DNS, web load, and a throughput check.
- Export router logs and note time ranges of issues.
- Record channel, RSSI, and client distance for RF problems.