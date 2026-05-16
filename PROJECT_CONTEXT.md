# AI RESIDENCY — PROJECT CONTEXT

**Owner:** Gus Neill  
**Live:** https://tryairesidency.com (Netlify, auto-deploys from GitHub)  
**GitHub:** https://github.com/gusjneill/tryairesidency  
**Stack:** Vanilla HTML/CSS/JS (no build step, single `index.html`)

---

## THE PRODUCT

**What it does:**  
Talent placement platform connecting Australian university AI students/recent grads with companies needing 4–12 week AI expertise stints. Gus takes a cut of day rate.

**Key numbers:**
- Day rates: **$300+** per day
- Placements: **4–12 weeks**
- Acceptance rate: **Top 5%** (fewer than 1 in 20)
- Team size: **Gus** (solo founder, strategy & ops background from Uber)

**Live sections:**
- Hero + trust signal + logos strip (Uber, Atlassian, Canva, Simon-Kucher)
- Why AI Residency (3 cards: industry-specific, onboarding, flexibility)
- Vetting process (3-step, dark section)
- 6 featured talent cards (uni/year/skills/bio)
- Support triage AI demo (interactive, randomised input → sorted output)
- Real testimonial from Gus (Strategy & Ops Manager, Uber)
- FAQ (7 Qs)
- Contact section (Calendly popup + Netlify Forms)
- Footer

---

## HOW TO WORK WITH GUS

### Writing & Communication

**North star:** True → Precise → Concise. In that order.

**Structure:**
- Lead with conclusion (so-what first)
- 3–5 bullets of evidence
- Close with next steps or action
- Never end with info alone

**Format:**
- Bullets over prose, always
- Capital letters to start bullets; no full stops (unless multi-sentence)
- Bold key numbers/points
- No em dashes, no ellipses, no "It's not X, it's Y"
- Traffic lights (🟢🟡🔴) for status only
- British English baseline, slightly Australianised internally
- No toxic positivity, no excessive buzzwords ("bandwidth," "boiling the ocean")

**Process (for any proposal):**
1. Structure first (sketch bullets)
2. Show Gus the structure + proposed changes
3. Wait for **"yes"** confirmation before coding
4. After approval: code → commit → push → deploy
5. Never assume permission; always ask first

**Tone:**
- Professional but not stiff
- Disagreement: "Curious why you think that makes sense?" (probe first, assert after)
- Uncertainty: "Still checking, will come back" OR full commitment. No hedging.
- Humor in conversation: fine. In writing to users: none (memes only).

**Red flags Gus hates:**
- Contradiction (sign of unclear thinking)
- Detail before frame (methodology before so-what)
- Walls of unstructured text
- Typos (signals low effort)
- Performative language (trying to sound smart instead of being useful)

---

## TECHNICAL SETUP

### Stack
- **Framework:** None. Single HTML file, ~1167 lines.
- **Hosting:** Netlify (auto-deploys from GitHub on `main` push)
- **Domain:** https://tryairesidency.com
- **DNS:** Managed via Netlify

### Key Files & Assets
```
tryairesidency/
├── index.html              (entire app; edit here)
├── assets/
│   └── images/
│       └── gus_neill_headshot.jpg  (Gus's testimonial photo)
├── netlify.toml            (Netlify config)
└── .git/                   (GitHub repo)
```

### External Dependencies
- **Calendly:** `calendly.com/gus-j-neill/30min` (popup embed)
  - Settings: Name display turned OFF (solved via Calendly UI)
  - Load: Async/defer script tag (faster popup)
- **Netlify Forms:** Wired to `gus.j.neill@gmail.com`
  - Talent application form
  - Company hiring inquiry form
- **Google Fonts:** Instrument Serif + Inter (preconnected)

### Key Integrations
- **Form submissions:** Netlify Forms (auto-emails Gus)
- **Logo display:** Currently text fallbacks (was Clearbit, broke)
  - **TODO:** Replace with local SVG assets or proper CDN logos
- **Dynamic content:**
  - Next month name (auto-updates via JS)
  - Current year (auto-updates via JS)
  - Randomised support triage demo (5 tickets, random input order)

---

## RECENT CHANGES (Last Session)

**Commit:** `c9ad812`  
**Message:** Fix: Calendly async load, logo fallbacks, Gus headshot, button routing, triage sorting

**Changes made:**
1. ✅ Calendly slow load — added `async defer` to widget script
2. ✅ Logo images broken — replaced Clearbit URLs with text fallbacks (Uber, Atlassian, Canva, Simon-Kucher)
3. ✅ Gus headshot — replaced generic Unsplash photo with `/assets/images/gus_neill_headshot.jpg`
4. ✅ "See more talent" button — changed from `onclick="openCalendly()"` to `href="#contact"` anchor link
5. ✅ Triage demo sorting — output tickets now sorted by urgency (urgent → high → med → low) after processing
6. ✅ Calendly name display — solved via Calendly settings (UI, not code)

**Note:** All changes committed locally. Push pending GitHub auth (need PAT or manual push from your machine).

---

## DEPLOYMENT WORKFLOW

### To deploy changes:

**Step 1: Push to GitHub**
```bash
cd tryairesidency
git push origin main
```
(If auth fails: use GitHub PAT or push from your local machine)

**Step 2: Netlify auto-deploys**
- Netlify watches `gusjneill/tryairesidency` `main` branch
- Deploy completes in ~1–2 min
- Live at https://tryairesidency.com

---

## COMMON EDITS

### Add a new talent card
- Find the `candidates-grid` section (around line 674)
- Copy a `candidate-card` div
- Update: `<img>`, name, title, bio, tags, availability
- Images: Use Unsplash URL or local asset in `/assets/images/`

### Update FAQ
- Find `#faq` section (around line 808)
- Add new `faq-item` with `.faq-q` and `.faq-a`
- JavaScript handles click-to-expand (no changes needed)

### Change color/branding
- Edit CSS vars in `:root` (lines 18–28)
- `--accent: #ff5b1f` (orange)
- `--bg: #fbf9f4` (cream)
- `--ink: #1a1a1a` (dark grey)

### Update Calendly URL
- Search `calendly.com/gus-j-neill/30min`
- Two places: line 996 (popup function) and line 998 (fallback URL)

### Change day rate in text
- Search `$300` or `$1,500 per week`
- Update in Why section (line 632) and FAQ (line 819)

---

## KNOWN ISSUES & TODOs

| Issue | Status | Action |
|-------|--------|--------|
| Logo images broken (Clearbit) | Open | Replace with local SVGs or proper CDN |
| Calendly name in popup | ✅ Resolved | Turned off in Calendly settings |
| Calendly slow load | ✅ Fixed | Added async/defer |
| Triage demo output unsorted | ✅ Fixed | Now sorts by urgency |
| GitHub push blocked | Open | Need PAT or local push |

---

## ANALYTICS & MONITORING

- **Form submissions:** Land in `gus.j.neill@gmail.com` (Netlify Forms)
- **No GA/Mixpanel tracking** currently
- **No A/B testing** set up

---

## FREQUENTLY NEEDED CONTEXT

**Q: I need to make a change. What's the process?**  
A: (1) Structure the change in bullets. (2) Show Gus. (3) Wait for **"yes"**. (4) Code + commit + push.

**Q: How long does deployment take?**  
A: ~1–2 minutes after pushing to `main`.

**Q: Can I edit CSS/design without touching HTML?**  
A: All CSS is in `<style>` block at top of `index.html`. Edit there, no separate file.

**Q: Where do form submissions go?**  
A: Both hiring + talent application forms → `gus.j.neill@gmail.com` via Netlify Forms.

**Q: How do I test changes before deploying?**  
A: Open `index.html` locally in a browser (works offline except Calendly/forms).

**Q: The site feels slow. What's the bottleneck?**  
A: Likely Calendly widget or Google Fonts. Already optimised with preconnect/async. Further gains need CDN/caching.

---

## GUSISMS (What works, what doesn't)

**✅ Gus likes:**
- Direct proposals with structure (bullets, so-what first)
- Confirmation before action
- Practical solutions, not theories
- Being asked, not assumed
- Work that gets done (not "optional" suggestions)
- Clarity on next steps

**❌ Gus dislikes:**
- Vague hedging ("might work," "could consider")
- Long prose explanations
- Changes without asking first
- Performative language ("It's important to note...")
- Being over-explained at
- Ending a proposal without a next step
- Generic "best practices" without context

**Engagement style:**
- Direct feedback expected
- Disagreement welcome (probe first approach)
- Show the options, wait for a choice
- Keep it instrumental (why does this matter *to Gus*?)
- No fluff, no padding

---

## FUTURE ROADMAP (Inferred)

- Replace logo text with actual SVG/CDN logos
- Add day rates to talent cards (currently hidden)
- Expand talent pool (currently 6 featured)
- Possibly add company testimonials beyond Gus
- A/B test call-to-action copy
- Expand to other ANZ regions (currently AU-only)

---

## CONTACT & QUESTIONS

- **Gus's email:** gus.j.neill@gmail.com
- **Gus's LinkedIn:** https://www.linkedin.com/in/gusneill/
- **Site feedback:** Form on contact section → email
