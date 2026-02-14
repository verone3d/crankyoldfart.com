# CrankyOldFart.com - Build Conversation Log
**Date:** February 14, 2026

---

## Background
- The original crankyoldfart.com website was lost. Only the main page image remained.
- The site was originally a gag retirement gift for a co-worker who called himself a "cranky old fart."
- The domain was available so it was purchased.
- It was a simple private club site - invite only, you have to be invited.

## What Was Built
- Single-page website with dark, gentleman's club aesthetic matching the splash image
- **Hero section:** Full-screen splash with the man-in-chair photo as background, "CrankyOldFart" title, tagline
- **The Club section:** Description of the private club
- **House Rules:** 5 rules in Roman numerals (invite only, don't talk about it, etc.)
- **Membership section:** Reinforces invite-only with badge
- **Enter button:** Clicking it triggers a buzzer sound and shows "UNAUTHORIZED" overlay with shaking red text. Click anywhere to dismiss.
- **Footer:** Email link (verone@crankyoldfart.com) in gold and "Get off our lawn" copyright
- Buzzer sound generated via Web Audio API (no sound files needed)

## Design Iterations
1. **Initial build:** Dark/moody gentleman's club aesthetic with muted gold text
2. **Too dark:** Brightened image from 0.3 to 0.6 brightness, bumped saturation
3. **Image sizing:** Tried `contain` to show full man but left black bars on sides - switched back to `cover`
4. **Text hard to read:** Swapped from Lato to Open Sans font, changed all text to white with dark text-shadows, brightened gold accents from #8b6914 to #d4a826
5. **Text centering:** Changed hero-content from relative to absolute positioning with translate(-50%, -50%) to center properly
6. **Image sharpness:** Tried CSS SVG convolution filter for sharpening - no visible improvement. Removed it.
7. **New image:** Replaced `crankyoldfart-com-splash.jpg` with `crankyoldfart-com-splash-2.jpg` - much sharper result
8. **Enter button:** Added border, hover effect, click triggers Web Audio buzzer + full-screen "UNAUTHORIZED" red overlay
9. **Email link:** Added mailto link for verone@crankyoldfart.com in footer

## Design Decisions
- Style: Dark background (#0a0a0a), white text with dark shadows for readability, bright gold (#d4a826) accents
- Font: Open Sans for body, Cinzel for headings, Playfair Display for tagline
- Image uses `cover` to fill full screen
- Image filter: brightness(0.6) saturate(0.85) to keep it visible but not overpowering
- Hero content uses absolute positioning centered with transform for proper centering

## Images Available
Located in: **C:\Users\veron\crankyoldfart\images**
- `crankyoldfart-com-splash-2.jpg` - **Currently used** hero image (sharper version)
- `crankyoldfart-com-splash.jpg` - Original hero image (slightly blurry)
- `me_02.png` / `me_03.png` - Cartoon avatar icons (not currently used on site)
- `Untitled.png` - Screenshot of site during development (can be removed)

Note: `tim_002.jpg` and `tim_new.webp` were previously in the folder but are no longer present.

## GitHub Setup
- **Repo:** git@github.com:verone3d/crankyoldfart.com.git
- **Visibility:** Public (required for GitHub Pages on free plan)
- **GitHub Pages:** Enabled, deploying from main branch
- **Custom domain:** crankyoldfart.com - ACTIVE and working
- **HTTPS:** Enabled and enforced - free SSL cert via GitHub/Let's Encrypt
- **SSL cert expires:** May 15, 2026 (auto-renewed by GitHub for free)
- **GitHub CLI:** Installed via winget (gh v2.86.0), authenticated as verone3d
- **Settings page:** https://github.com/verone3d/crankyoldfart.com/settings/pages

## DNS Records at GoDaddy
### For GitHub Pages (website):
| Type  | Name | Value             |
|-------|------|-------------------|
| A     | @    | 185.199.108.153   |
| A     | @    | 185.199.109.153   |
| A     | @    | 185.199.110.153   |
| A     | @    | 185.199.111.153   |
| CNAME | www  | verone3d.github.io |

### For Email (cPanel at GoDaddy):
| Type | Name | Priority | Value                  |
|------|------|----------|------------------------|
| MX   | @    | 0        | mail.crankyoldfart.com |
| A    | mail | -        | (cPanel server IP)     |

## Hosting Considerations
- **GitHub Pages** handles hosting + free auto-renewing SSL for the website
- **No GoDaddy hosting needed** for the website itself
- **GoDaddy still needed for:** domain registration + cPanel email
- **If wanting to drop GoDaddy hosting entirely**, email needs to move to:
  - Zoho Mail (free for 1 domain, up to 5 users)
  - Google Workspace ($6/month)
  - Cloudflare Email Routing (free, forwards to personal email)
- **Cloudflare** recommended for other sites: free SSL forever, auto-renewed, plus CDN/DDoS protection
- cPanel AutoSSL may already be available - check cPanel > SSL/TLS Status > Run AutoSSL

## Tools Installed During Session
- **GitHub CLI (gh)** v2.86.0 - installed via `winget install GitHub.cli`
- Authenticated as `verone3d` via SSH protocol

## Git Commit History
1. `94ad59a` - Initial commit - CrankyOldFart.com private club website
2. `5fcbf78` - GitHub Pages CNAME file (auto-generated)
3. `f35234b` - Add conversation log with build notes, DNS setup, and TODOs
4. `ed3f598` - Update hero image to sharper version (splash-2)

## TODO
- [ ] Decide on email hosting if wanting to drop GoDaddy hosting
- [ ] Consider Cloudflare for other sites' SSL issues
- [ ] Consider changing "Est. Since We Stopped Caring" subtitle if desired
- [ ] Clean up unused images (Untitled.png screenshot)
