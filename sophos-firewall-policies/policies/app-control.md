
# Application Control Policy

## 🎯 Purpose
Prevent access to high-risk or productivity-draining applications while allowing essential business apps.

## ❌ Blocked Applications
- BitTorrent Clients (uTorrent, qBittorrent)
- VPN Tools (Psiphon, Hotspot Shield)
- Messaging (Telegram Desktop)
- Video Conferencing (Zoom – upload only)

## ⚖️ Throttled Applications
- Google Drive (Uploads)
- Dropbox (Sync)

## ✅ Allowed Applications
- Microsoft Outlook
- Microsoft Teams
- SAP ERP Client

## 🛠️ Enforcement
- Uses Sophos DPI engine
- Tied to MAC group: `Staff-PCs`
- Reports generated for attempted usage
