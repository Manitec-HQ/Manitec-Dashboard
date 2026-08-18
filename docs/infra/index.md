# Infrastructure Overview

![Manitec Infrastructure](https://i.postimg.cc/Y9LH6BbL/image_2.jpg)

Manitec Future (LLC) runs lean and sovereign. No Big Cloud lock-in — tools stacked for control.

## The Stack

```
Cloudflare (DNS/CDN)
  ├── DashNex (marketing/landings → manitec.pw, joesfaves.com)
  ├── Render (FastAPI backends → mail.manitec.pw)
  ├── Vercel (Next.js apps → chat, hex, dash, kairos, plex-sable, one-system)
  ├── GitHub Pages (docs → info.manitec.pw)
  └── Zoho Mail360 (email API)
```

## Services

| Category | Service | URL | Purpose |
|----------|---------|-----|---------|
| Domain | manitec.pw | [manitec.pw](https://manitec.pw) | Brand home |
| Docs KB | info.manitec.pw | [info.manitec.pw](https://info.manitec.pw) | This site |
| Mail | mail.manitec.pw | [mail.manitec.pw](https://mail.manitec.pw) | Inbox |
| Chat | ManiBot | [chat.manitec.pw](https://chat.manitec.pw) | Empire face |
| Chat | HexBot | [hex.manitec.pw](https://hex.manitec.pw) | Ops assistant |
| Dashboard | Control Hub | [dash.manitec.pw](https://dash.manitec.pw) | Ops + Room |
| Search | Kairos | [kairos-orcin-eight.vercel.app](https://kairos-orcin-eight.vercel.app) | AI search |
| Product | ONE System | [one-system-mu.vercel.app](https://one-system-mu.vercel.app) | Workshop v1 |
| Private | Plex-Sable | plex-sable.vercel.app | Joe only |
| DNS/CDN | Cloudflare | — | Speed + security |
| Deploy | Vercel | vercel.com/manitecs-projects | Primary |
| Email API | Zoho Mail360 | — | Transactional |

!!! note "Stale action items removed"
    Control Hub deploy and cyberpunk treatment on manitec.pw were already done. Firebase key hygiene stays an ops note, not a public action list.

## Detailed Docs

- [Tools & Services](./tools.md)
- [DashNex System Summary](./dashnex-system-summary.md)
- [DashNex Page Build Checklist](./dashnex-page-build-checklist.md)
- [Oracle Cloud](./oracle-cloud.md)
- [GenX Router API](./genx-router.md)

[Philosophy](../philosophy/) | [Projects](../projects/)
