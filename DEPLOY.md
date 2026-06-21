# MOST® website — deployment guide

This folder is a complete static website. No build step, no database, no framework.
Any static host serves it as-is.

## Contents
- index.html — the entire site (design, content, motion)
- favicon.ico / favicon.svg / favicon-16.png / favicon-32.png / apple-touch-icon.png
- og-image.png — link preview image (LinkedIn, WhatsApp, iMessage)
- robots.txt

## Hosting (pick one, all have free tiers)
1. **Cloudflare Pages** (recommended): dash.cloudflare.com → Workers & Pages → Create →
   Upload assets → drag this folder. Free, fast EU edge, free SSL.
2. **Netlify**: app.netlify.com/drop → drag this folder. Done.
3. **Vercel**: vercel.com/new → upload. Done.
4. Any classic host (OVH, home.pl): upload contents to the public_html folder via FTP.

## Connecting the domain (after purchase)
1. In the host's dashboard: add custom domain (e.g. most.consulting + www).
2. At the registrar: point DNS — CNAME `www` to the host's target, and the apex per
   the host's instructions (Cloudflare handles both automatically if the domain is on Cloudflare).
3. SSL is automatic on all hosts above. Force HTTPS in settings.
4. In index.html, replace the canonical/og:url comment in <head> with the real domain.

## Before real launch — the placeholder swap
The site currently shows labeled placeholder blocks. Replace when assets exist:
- Hero: swap the gradient in `.hero` for a <video> loop or background-image (see media note top-right of hero).
- Founder portrait + 3 foundation photos: replace the .photo divs' backgrounds with real images
  (`background:url(photo.jpg) center/cover`). Keep the warm grade — never cold blue.
- Two film bands (.film): wrap in <a> to the video, or embed <video> when films exist.
- Newsletter editions: update titles/dates to real Substack editions; link the Substack URL
  (two places: "Read and subscribe" + footer).
- Contact: replace `#` in the "Book 20 minutes" button with a Calendly/Cal.com link.
- Email: currently the personal Gmail — switch to the domain email once it exists.

## Editing text
Everything is plain HTML in index.html. Open in any editor, search for the sentence, change it.
No tooling needed.

## Email on the domain
At the registrar or via Cloudflare Email Routing (free), forward hello@yourdomain to your inbox,
or use a mailbox provider for sending. Outreach should come from the domain, not Gmail.
