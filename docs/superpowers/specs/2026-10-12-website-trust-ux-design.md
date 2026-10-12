# Merra Booking website trust and UX design

**Status:** Implemented and published
**Date:** 2026-10-12  
**Scope:** Static pre-launch website at `merrabooking.me`

## Goals

- Present Merra Booking honestly as an independent pre-launch project.
- Provide public privacy, data-deletion, terms, and cookie information suitable for Meta review.
- Avoid exposing user data or making unsupported production claims.
- Make the primary conversion path clear while the WhatsApp demo bot is still in development.
- Improve mobile navigation, accessibility, content hierarchy, and trust without inventing testimonials or metrics.
- Reduce third-party data transfer by self-hosting the website fonts.

## Current product status

The public website is a static GitHub Pages site. It has no registration, payment, analytics, advertising pixels, marketing trackers, or public user-generated content. The WhatsApp button may open a pre-launch/demo contact, but the bot is still under development and must not be represented as a guaranteed booking service.

OpenAI is used only for private testing and must not appear in public website copy or legal pages. Claude API is the intended future AI provider and may be named publicly only as a conditional provider when an AI feature is actually enabled.

## Legal and trust surfaces

### Privacy policy

Keep `/privacy.html` public and accessible without authentication. It must:

- identify Ramazanov Adil Daniyarovich as the current individual operator and list `team@merrabooking.me`;
- state the pre-launch/demo status and lack of IP/LLP registration without presenting a fictional company;
- distinguish the static website from any future WhatsApp bot;
- describe only actual data flows and providers;
- remove OpenAI from public disclosures;
- mention Claude only conditionally for a future enabled AI feature;
- state that the public site does not expose phone numbers, names, conversations, bookings, or other user data;
- disclose external resources only if they remain in use;
- explain rights and the public data-deletion process.

### Data deletion

Keep `/data-deletion/` public as the Meta Data Deletion Instructions URL. Use `team@merrabooking.me`, describe the information needed to identify a request, and avoid promising deletion of data that the demo system does not actually retain.

### Terms of use

Add `/terms.html` in Russian and English. Cover:

- pre-launch/demo status;
- use of the site and any demo contact on an “as is” basis;
- no guarantee that the WhatsApp bot is available or will complete a booking;
- prohibition on sending passwords, payment-card data, medical data, identity documents, or other sensitive information;
- prohibited abuse, spam, scraping, attacks, and attempts to bypass controls;
- third-party WhatsApp/Meta terms;
- intellectual-property ownership;
- contact email;
- a neutral statement that legal questions are subject to applicable law and professional review.

### Cookies and external resources

Self-host the display fonts and remove Google Fonts requests. Add a concise cookies section to the privacy policy or a dedicated `/cookies.html` page only if the implementation introduces a separate cookies surface. For the current static site, state that optional analytics and marketing cookies are not used. Disclose only necessary security mechanisms that are actually present through Cloudflare.

## UX and information architecture

The homepage order will be:

1. Header with logo, no more than six navigation items, and one primary CTA.
2. Hero explaining who Merra Booking is for, what it does, and the business benefit.
3. Visible pre-launch status strip: “Demo в разработке”.
4. Problem-to-solution section covering missed messages, manual scheduling, and repeat-customer loss.
5. Product-in-action flow: WhatsApp → Control Panel → loyalty/inventory/1C.
6. Capabilities section using existing product claims that can be supported.
7. Three-step “how it works” section.
8. About/project section identifying the independent pre-launch status.
9. Final CTA with WhatsApp and email paths.
10. Footer with product links, legal links, contact email, and data-deletion link.

Do not add fabricated customer logos, testimonials, adoption numbers, conversion rates, or “live” claims. WhatsApp CTAs must retain their destination but visibly communicate that the demo is in development.

## Accessibility and responsive behavior

- Preserve the existing dark visual identity and amber/teal accents.
- Keep visible keyboard focus states for links and CTA controls.
- Preserve reduced-motion behavior.
- Maintain logical heading order and landmark semantics.
- Ensure muted text remains readable against the dark background.
- Replace the current mobile behavior that hides all navigation with a compact accessible navigation solution.
- Ensure CTA targets and legal links remain usable at narrow widths.

## Technical changes

- Add local font assets and update CSS/font declarations.
- Update `index.html` content, metadata, status messaging, and navigation.
- Update `privacy.html` and `data-deletion/index.html` for the new contact and factual processing disclosures.
- Add `terms.html` and any required legal navigation links.
- Add or update cookie disclosure content.
- Preserve `robots.txt` and `sitemap.xml`.
- Do not change Cloudflare DNS, email routing, or security rules from repository code.

## Validation

Before publication:

- Parse all HTML pages and `sitemap.xml`.
- Verify every internal link and every legal page URL.
- Search for stale email addresses and unsupported OpenAI claims.
- Confirm no user phone numbers, names, conversations, or booking records appear in public page content.
- Check responsive breakpoints and keyboard focus behavior in a browser.
- Run `git diff --check`.
- Review the final diff before any push.

## Non-goals

- No production WhatsApp bot implementation.
- No analytics, marketing pixels, cookie-consent platform, user accounts, payments, or database UI.
- No Cloudflare dashboard changes in the website repository.
- No legal claim that the text guarantees compliance in every jurisdiction.
