# 🎤 Debate Platform - Product Plan

## 📌 Overview

A web-based, OBS-ready debate platform allowing participants to join structured debates with audio/video. Designed for streaming or recording via a browser source in OBS. Built with peer-to-peer WebRTC (no central video hosting), and lightweight moderation tools like timers and speaker control.

---

## 🛠️ MVP Goals

### Core Features

- [ ] Create & join debate "rooms"
- [ ] Peer-to-peer audio/video via WebRTC
- [ ] Role-based system: Moderator & Speakers (no viewers)
- [ ] Audio-only toggle
- [ ] Timer/clock for speaking turns
- [ ] Clean composited layout rendered for OBS (via browser source URL)

### Technical Stack

- **Frontend:** Next + TailwindCSS
- **Signaling Server:** Node.js + WebSocket (peer discovery)
- **Media:** Native WebRTC APIs (peer-to-peer)
- **Hosting:** Vercel
- **Clerk:** Auth Login
- **Database:** Supabase
- **Payments** lemonsqueezy

---

## 🧪 Phase 2 – Enhanced UX

### Moderation Tools

- [ ] Mute/unmute speakers
- [ ] Speaking queue or control system
- [ ] Kick/ban participant
- [ ] Audio level indicators (voice activity)

### Layout & OBS View

- [ ] Dynamically responsive grid for OBS embed
- [ ] Name labels & roles shown in layout
- [ ] Show/hide inactive users
- [ ] Browser source output URL (clean, no controls)

---

## 🚀 Future Features

- [ ] Real-time overlay elements (timers, names, etc.)

---

## 🔐 Access & Security

- [ ] Join via tokenized link (no login needed)
- [ ] Role-based access (Moderator / Speaker)
- [ ] Optional room password or expiring links

---

## 🧱 Architecture Sketch

[ Participant A ] ←→ [ WebRTC P2P ] ←→ [ Participant B ] ↓ ↑ [ WebSocket Signaling Server ] (Room & peer discovery) ↓ ↑ [ Nuxt Frontend = Rendered Output for OBS ]

- No viewer role — layout rendered by browser for OBS capture
- Peer connections managed via signaling and STUN/TURN
- All layout/styling controlled in the frontend

---

## 📆 Timeline

| Week | Goal                                            |
| ---- | ----------------------------------------------- |
| 1    | Setup Next project, base layout & room joining  |
| 2    | Build signaling server (Node + WebSocket)       |
| 3    | Add peer connection logic with audio/video      |
| 4    | Layout the OBS panel + speaking timer           |
| 5    | Role-based tools (mute, kick) + polish OBS view |

---

## 🔗 References

- [WebRTC API (MDN)](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
- [Socket.io or native WebSocket](https://socket.io/)
- [OBS Browser Source Docs](https://obsproject.com/wiki/Browser-Source-Guide)
- [Clerk Auth](https://clerk.com/docs)
- [Payments](https://docs.lemonsqueezy.com/api)
- [Valid STUN List](https://raw.githubusercontent.com/pradt2/always-online-stun/master/valid_hosts.txt) This gets updated everyhour

---

## ✅ MVP Success Criteria

- Up to 8 participants in a room with working audio/video
- Moderator has basic control (mute, timers)
- OBS can capture panel via clean browser source URL
- Stable P2P streaming performance during session
