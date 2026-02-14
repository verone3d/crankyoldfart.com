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
- **Enter button:** Clicking it triggers a buzzer sound and shows "UNAUTHORIZED" overlay
- **Footer:** Email link (verone@crankyoldfart.com) and "Get off our lawn" copyright
- Buzzer sound generated via Web Audio API (no sound files needed)

## Design Decisions
- Style: Dark background, white text with dark shadows for readability, bright gold (#d4a826) accents
- Font: Open Sans for body, Cinzel for headings, Playfair Display for tagline
- Image uses `cover` to fill full screen (tried `contain` but left black bars on sides)
- Image filter: brightness(0.6) saturate(0.85) to keep it visible but not overpowering
- CSS sharpening was attempted but didn't make a noticeable difference on the source image

## Images Available
- `crankyoldfart-com-splash.jpg` - Main hero image (currently used, slightly blurry - needs better version)
- `tim_002.jpg` - Similar photo, different glasses
- `tim_new.webp` - Similar photo
- `me_02.png` / `me_03.png` - Cartoon avatar icons
- `untitled.png` - Screenshot of site (can be removed)

## GitHub Setup
- **Repo:** git@github.com:verone3d/crankyoldfart.com.git
- **Visibility:** Public (required for GitHub Pages on free plan)
- **GitHub Pages:** Enabled, deploying from main branch
- **Custom domain:** crankyoldfart.com configured
- **HTTPS:** Pending - GitHub needs DNS to propagate before issuing free SSL cert
- Check status at: https://github.com/verone3d/crankyoldfart.com/settings/pages

## DNS Records Needed at GoDaddy
### For GitHub Pages (website):
| Type  | Name | Value             |
|-------|------|-------------------|
| A     | @    | 185.199.108.153   |
| A     | @    | 185.199.109.153   |
| A     | @    | 185.199.110.153   |
| A     | @    | 185.199.111.153   |
| CNAME | www  | verone3d.github.io |

### For Email (cPanel):
| Type | Name | Priority | Value                  |
|------|------|----------|------------------------|
| MX   | @    | 0        | mail.crankyoldfart.com |
| A    | mail | -        | (cPanel server IP)     |

## Hosting Considerations
- **GitHub Pages** handles hosting + free SSL for the website (no GoDaddy hosting needed for the site)
- **GoDaddy still needed for:** domain registration + cPanel email
- **If wanting to drop GoDaddy hosting entirely**, email needs to move to:
  - Zoho Mail (free for 1 domain, up to 5 users)
  - Google Workspace ($6/month)
  - Cloudflare Email Routing (free, forwards to personal email)
- **Cloudflare** recommended for other sites: free SSL forever, auto-renewed, plus CDN/DDoS protection
- cPanel AutoSSL may already be available - check cPanel > SSL/TLS Status > Run AutoSSL

## TODO
- [ ] Supply a higher quality/sharper hero image
- [ ] Verify DNS propagation and enable HTTPS enforcement
- [ ] Decide on email hosting if dropping GoDaddy hosting
- [ ] Consider Cloudflare for other sites' SSL issues
- [ ] Consider changing "Est. Since We Stopped Caring" subtitle if desired
