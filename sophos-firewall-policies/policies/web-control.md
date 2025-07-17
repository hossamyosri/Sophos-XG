
# Web Filtering Policy

## 🎯 Purpose
Block or restrict access to time-wasting, unsafe, and non-work-related websites during work hours.

## 🕸️ Categories Blocked
- Social Networking (Facebook, Instagram, etc.)
- Adult Content
- Video & Streaming (YouTube, Netflix)
- Gambling
- Ads & Trackers

## 📁 File Types Blocked
- `.exe`, `.torrent`, `.mp4`, `.zip`
- Based on potential risk and misuse

## 🕓 Scheduling & Quota
- Active: Monday–Friday, 9AM–5PM
- YouTube Quota: 30 minutes per user per day

## 🛠️ Enforcement
- DPI engine used for deeper URL inspection
- HTTPS decryption enabled for full control
- Policy applied to group: `Staff-PCs`
