<wizard-report>
# PostHog post-wizard report

The wizard has completed a deep integration of PostHog analytics into the markusharrison.com portfolio site. This is a static HTML site served via GitHub Pages, so PostHog was integrated via the JavaScript snippet in `index.html`.

**Summary of changes to `index.html`:**
- Replaced the placeholder `YOUR_PROJECT_API_KEY` in the PostHog init with the real project token and updated the config to include `defaults: '2026-01-30'` and `capture_exceptions: true` for automatic exception tracking. Removed the manual `$pageview` capture from the `loaded` callback — PostHog captures pageviews automatically.
- Fixed two incorrect event captures: the first project card was labelled `'Orbit UI'` (corrected to `'Costco Business Delivery'`), and the Nostalgic Vault card had an empty `project_name` (corrected to `'Nostalgic Vault'`).
- Added `hero_cta_clicked` captures to the "View Projects" and "Get in Touch" hero buttons with a `cta_label` property.
- Added `resume_downloaded` captures to all three Download Resume links (desktop nav, mobile nav, footer) with a `location` property.
- Added `contact_initiated` captures to the header "Contact Me" button, the About Me "Email Me" link, the footer email icon, and the footer "Email Me" CTA, each tagged with `location` and `method` properties.
- Added `social_link_clicked` captures to the GitHub and LinkedIn footer icons with a `platform` property.

| Event | Description | File |
|---|---|---|
| `project_clicked` | User clicks a project card image or title (breakdown: `project_name`, `project_type`) | `index.html` |
| `hero_cta_clicked` | User clicks "View Projects" or "Get in Touch" in the hero section (breakdown: `cta_label`) | `index.html` |
| `resume_downloaded` | User clicks any Download Resume link (breakdown: `location`) | `index.html` |
| `contact_initiated` | User clicks any contact or email CTA (breakdown: `location`, `method`) | `index.html` |
| `social_link_clicked` | User clicks a social icon in the footer (breakdown: `platform`) | `index.html` |

## Next steps

We've built some insights and a dashboard for you to keep an eye on user behavior, based on the events we just instrumented:

- [Analytics basics dashboard](/dashboard/1644431)
- [Project clicks by project](/insights/ke1nt72f)
- [Contact initiations over time](/insights/xquChgDT)
- [Resume downloads over time](/insights/YHraLs9C)
- [Social link clicks by platform](/insights/l8Bjkr4c)
- [Hero CTA clicks](/insights/NnjPgvlS)

### Agent skill

We've left an agent skill folder in your project. You can use this context for further agent development when using Claude Code. This will help ensure the model provides the most up-to-date approaches for integrating PostHog.

</wizard-report>
