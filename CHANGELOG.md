# Changelog

---

## [6.39.85] — 2026-05-22

### Added
- 8 background themes: Midnight, Ocean, Nebula, Forest, Aurora, Ember, Slate, Light
- 8 accent colour options with live preview in settings
- Custom scrollbar throughout the app
- Show/hide password toggle on all password fields
- Message delivery receipt ticks — grey on send, green on delivery
- Profile photo upload and removal
- Display name and password change in settings
- Modals close when clicking outside
- PWA support — installable from browser on iOS and Android
- Service worker for offline caching
- security.txt at /.well-known/security.txt
- Full security headers: CSP, HSTS, Permissions-Policy, Referrer-Policy, X-Frame-Options
- HTTP to HTTPS redirect enforced

### Changed
- Font changed to Inter for body text, JetBrains Mono kept for monospaced elements
- Auth screen redesigned with animated hex, grid background, glow
- Settings modal rebuilt with sticky header and footer, scrollable body
- Compose placeholder simplified
- Sidebar preview no longer shows [encrypted]

### Fixed
- Call loop caused by auto-decline firing on active calls
- Service worker no longer intercepts Google Fonts requests
- Light theme rendering across all modals and overlays
- Auto-scroll on conversation open now waits for images to load

---

## [6.39.84] — 2026-05-20

### Added
- Voice and video calls via LiveKit Cloud
- Incoming call alert with accept and decline
- Multi-device call handling
- Call timer, mute, camera toggle, fullscreen
- GIF search and sending via Giphy
- Real-time messaging via Go WebSocket server
- Online presence indicators
- Typing indicators

### Fixed
- Messages not appearing in real time without a page refresh
- Call disconnect loop from LiveKit Cloud silence detection
- Caller receiving their own incoming call alert

---

## [6.39.00] — 2026-05-18

### Added
- Initial production release
- End-to-end encrypted messaging, Signal Protocol with Double Ratchet
- WebAuthn and TOTP 2FA
- Breach detection on login
- Admin portal
- Browser extension published to Chrome Web Store
- Desktop builds for Linux and Windows

### Security
- 13 vulnerabilities fixed before launch
- Per-account lockout
- Timing oracle on login fixed
- Host header injection fixed in 6 routes
- Backup code entropy increased
- Invite acceptance race condition fixed
- Multi-stage Docker builds with non-root user
- Rate limiting on auth endpoints
- Database user restricted to DML only
