<div align="center">

# HexChat

Private messaging, built for real privacy.

[![Live](https://img.shields.io/badge/live-hexchat.co.uk-1D9E75?style=flat-square&logo=googlechrome&logoColor=white)](https://hexchat.co.uk)
[![Chrome Extension](https://img.shields.io/badge/chrome-extension-4285F4?style=flat-square&logo=googlechrome&logoColor=white)](https://chromewebstore.google.com/detail/hexvault/bmjflnnopehafhmelobgbjeobdhokifj)
[![Version](https://img.shields.io/badge/version-6.39.85-555?style=flat-square)](./CHANGELOG.md)

</div>

---

HexChat is a self-hosted encrypted messaging app I built from scratch. It runs on my own hardware, traffic goes through a Cloudflare Tunnel so there are no open ports on my network, and the server never sees message contents.

It started as a personal project to learn how end-to-end encryption actually works in practice. It has since grown into something I use daily and am continuing to develop.

---

## What it does

- End-to-end encrypted messaging using the Signal Protocol (Double Ratchet)
- Voice and video calls via LiveKit
- GIF support
- Installable as a PWA on iOS and Android
- Real-time presence, typing indicators, delivery receipts
- Profile photos, custom themes, accent colour picker
- 2FA via TOTP and WebAuthn
- Breach detection on login
- Browser extension on the Chrome Web Store

---

## Coming next

- Voice notes
- Group chats
- Push notifications
- Desktop app

---

## Stack

The backend is a Flask API with a Go WebSocket server handling real-time connections. Everything runs in Docker on a VMware ESXi box at home.

| Layer | Technology |
|---|---|
| Frontend | Vanilla JS, PWA, Service Worker |
| API | Python, Flask, Gunicorn |
| Real-time | Go |
| Database | PostgreSQL 16 |
| Cache | Redis 7 |
| Object store | Garage (S3-compatible) |
| Reverse proxy | Caddy |
| Tunnel | Cloudflare Tunnel |
| Calls | LiveKit Cloud |
| TURN | Metered |

---

## Security

The server is zero-knowledge by design. Messages are encrypted before they leave the client. The server stores ciphertext only.

A full audit pass identified and fixed 13 vulnerabilities before launch, covering session handling, timing attacks, rate limiting, host header injection, and backup code entropy. Security headers (CSP, HSTS, Permissions-Policy, Referrer-Policy) are enforced at the Caddy layer.

To report a vulnerability see [SECURITY.md](./SECURITY.md) or email security@hexchat.co.uk.

---

## Changelog

See [CHANGELOG.md](./CHANGELOG.md).

---

<div align="center">
hexchat.co.uk
</div>
