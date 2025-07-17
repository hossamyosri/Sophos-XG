
# MAC Address Grouping Policy

## 🎯 Objective
Segment devices/users in the network without VLANs by creating MAC Address groups. Each group will have different firewall and filtering policies assigned.

## 📋 Group Definitions
### 1. Staff-PCs
- 🔒 Most restrictive group
- Applies strict Web + App filtering
- Intended for standard employee workstations

### 2. Management
- 🧩 Moderate restrictions
- Allows access to more categories such as LinkedIn, YouTube (limited)
- No bandwidth throttling

### 3. Personal Devices
- 📱 Phones, Tablets, Guest Laptops
- Minimal restrictions, but blocked from LAN access
- Only Internet access is allowed (No RDP/SMB etc.)

## 🛠️ Implementation Notes
- MACs are added manually via Sophos Admin UI
- Static grouping used
- Used group membership in Firewall, Web Filtering, and App Control
