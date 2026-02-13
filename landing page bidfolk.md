# bidfolk Landing Page — Project Notes

## What We Built
A privacy policy landing page for bidfolk, linked from LinkedIn event registration forms. Also includes a minimal "coming soon" root page.

**Live URLs:**
- Privacy policy: https://bidfolk.com/policy
- Root page: https://bidfolk.com

---

## Privacy Policy Content

**What we collect:** Name and email address via LinkedIn event registration.

**How we use it:** To send invitations to bidfolk community events (~twice a month). That's it.

**Key promise:** We will never use their information for newsletters, marketing, or any other purpose without asking permission first.

**Third-party sharing:** We do not share, sell, or provide personal information to third parties. Data stays with bidfolk.

**Data storage:** Stored securely, only accessible to the bidfolk team.

**Rights:** Users can request to see, update, or delete their information by emailing heather@bidfolk.com.

**Contact:** heather@bidfolk.com

---

## Strategic Decisions

### Privacy Policy — Specific vs. Vague
Decided to be **specific and honest** rather than vague. Reasons:
- Vague language creates more legal exposure, not less (GDPR, CAN-SPAM require stated purpose)
- Specific policies build trust, which increases signups
- Includes a clear path to expand later (ask permission before new uses)

### Email Data — Don't Share with Platforms
Future business model: charge platforms to be featured at bidfolk events. **Do not share attendee emails with platforms.** Reasons:
- The community is the product — sell access, not the list
- Platforms pay for event sponsorship, speaking slots, demo time
- Keeps audience trust intact and growing
- Simpler privacy compliance ("we don't share with third parties")
- Model: conferences sell booths, podcasts sell ad spots, newsletters sell sponsored content

### Email Collection
- LinkedIn handles registration and email collection
- Emails managed in Google Sheets
- Used for bi-monthly event invitations only

---

## Branding

- **bidfolk** is always lowercase
- Background: dark navy/charcoal (#232a35 / #2b3340)
- Text: white (#f0f2f5)
- Accent: teal green (#3ac9a2) — used on the "o" in the logo
- Font: Outfit (Google Fonts)
- Favicon: teal "o" ring on dark rounded square (SVG)
- Logo file: `bidfolk (new).png`

---

## Hosting & Infrastructure

### GitHub Pages
- Repo: https://github.com/heathermltn56-ai/bidfolk-policy
- Branch: main
- Folder: / (root)
- Custom domain: bidfolk.com

### File Structure
```
/
├── index.html              # "Coming soon" root page
├── policy/index.html       # Privacy policy page
├── favicon.svg             # Teal "o" favicon
├── bidfolk (new).png        # Logo (also used as apple touch icon)
├── CNAME                   # Custom domain config for GitHub Pages
└── landing page bidfolk.md  # This file
```

### DNS (GoDaddy)
**A records (already configured):**
- @ → 185.199.108.153
- @ → 185.199.109.153
- @ → 185.199.110.153
- @ → 185.199.111.153

**CNAME:**
- www → bidfolk.com (existing, works via A record chain)

**Do not touch — Gmail/email records:**
- 5 MX records (aspmx.l.google.com and alternates)
- TXT SPF record (v=spf1...)
- TXT DMARC record (_dmarc)
- TXT Google Workspace recovery verification
- CNAME Google domain verification (o6letj7klz7c)
- CNAME _domainconnect (GoDaddy system)

**Unknown records (not affecting anything):**
- CNAME policy → dns1.p04.nsone.net
- CNAME policy2 → dns2.p04.nsone.net
- CNAME policy3 → dns3.p04.nsone.net
- CNAME policy4 → dns4.p04.nsone.net
- Origin unknown, safe to delete later if confirmed unused

### HTTPS
- GitHub auto-provisions SSL certificate via Let's Encrypt
- "Enforce HTTPS" checkbox becomes available ~15-30 min after DNS verification
- Check the box once available in repo Settings > Pages

---

## To-Do / Future

- [ ] Enable "Enforce HTTPS" once certificate is issued
- [ ] Investigate and clean up unknown policy/policy2/3/4 CNAME records
- [ ] Build out bidfolk.com root page when ready
- [ ] If adding newsletter or other email uses, update privacy policy and ask existing subscribers for consent
