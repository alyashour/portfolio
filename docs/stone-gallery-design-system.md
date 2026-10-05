# Stone Gallery · v1

Personal portfolio for Aly Ashour · alyashour.com

Historical foundation. The current live direction and future-image requirements are documented in [Perception Atelier](perception-atelier-design-system.md), which takes precedence for image-derived page palettes and vision annotations.

## Design intent

Warm, quiet, curated. A museum catalogue for engineering work: expressive serif headlines, precise sans-serif text, large project visuals and restrained numbered captions. Classical art and personal photography add character; transformer software, PCBs and LiDAR explain the work. The sculpture is a source of tone and composition, not the default image for every project.

## Color

| Token | Hex | Role |
| --- | --- | --- |
| Ivory | #F1E9DB | Main canvas |
| Paper | #FAF6EF | Secondary surface, code background |
| Limestone | #D5C4A7 | Decorative fills, subtle hover surfaces |
| Taupe | #8B7355 | Decorative accent; large type only |
| Espresso | #342A22 | Body, headings, primary controls |
| Muted ink | #6C5946 | Secondary text and metadata |
| Rule | #C4B49E | Decorative dividers, not input boundaries |
| Focus | #594432 | Keyboard focus and primary hover |
| Error | #8C392B | Error text plus descriptive message |
| Success | #40583F | Success text plus descriptive message |

Use espresso and muted ink for normal text. Taupe does not reach 4.5:1 on ivory, so do not use it for small captions or controls. Light dividers never communicate an essential state alone. Technical data may retain meaningful colors and must include a legend.

## Typography

Playfair Display 400 for name, hero and headings; Inter 400/500/600 for prose and interface; IBM Plex Mono 400 for code, technical annotations and units only. Georgia, system-ui and ui-monospace are fallbacks. The live specimen loads fonts from Google Fonts; self-host WOFF2 before production integration when possible.

| Role | Size / line height | Details |
| --- | --- | --- |
| Hero | 48–104px / 1.05 | Fluid; -0.04em tracking |
| Section title | 32–56px / 1.15 | -0.025em tracking |
| Project title | 24px / 1.25 | Serif, normal tracking |
| Body | 16px / 1.65 | Max 65 characters per line |
| Navigation | 14px / 1.5 | Sans-serif |
| Caption | 13px / 1.5 | Sentence case |
| Eyebrow | 12px / 1.5 | Uppercase, 0.14em tracking |
| Code | 12–14px / 1.6 | Scroll within code block |

Avoid justified prose, long all-capital paragraphs and serif technical labels. Use one h1 per page and a logical heading sequence.

## Layout and spacing

4px base unit. Scale: 4, 8, 12, 16, 24, 32, 48, 64, 96px. Content width 1280px, reading width 65ch, fluid side gutters 20–64px. Desktop hero uses an asymmetric text/image split; mobile stacks text before media. Sections use 64–96px breathing room, reduced to 48px on mobile. Primary layout breakpoint: 768px; two-column layouts become one column. Use content-driven additional breakpoints when needed. Keep images fluid and allow navigation to wrap.

## Components

- Header: serif name at left, quiet text navigation at right; active link has underline and aria-current. On mobile, wrap navigation instead of hiding it behind a menu in v1.
- Project preview: linked image, fine divider, numbered caption and serif title. Use actual project names, short summary and technology metadata. No framed card shadow. Hover underlines the title; keyboard focus outlines the link.
- Project index: numbered rows with title, discipline and arrow; 44px minimum link height. Optional filters use semantic buttons with aria-pressed.
- Case study: title, concise problem statement, role and dates; then approach, evidence, results and limitations. Technical screenshots remain readable at full color, with descriptive captions. Do not invent outcomes.
- Buttons: espresso primary, transparent outlined secondary; 2px corner radius, 44px minimum height. Disabled controls have native disabled semantics.
- Text links: underline in prose; arrow may accompany navigation links but never replaces a label.
- Inputs: visible label, paper surface, muted ink boundary, persistent helper text. Errors use aria-invalid and aria-describedby plus a textual explanation. Specimen fields are demonstrations, not a working contact form.
- Technical figures: clean transformer block diagrams, unfiltered PCB photos, LiDAR point clouds with appropriate scale/legend. Any generated imagery is explicitly marked as illustrative.

## Imagery

Use 3:2 project thumbnails and an intentional hero crop. Never place essential text over busy imagery. Retain natural technical colors: no blanket sepia filter on PCBs, plots or point clouds. Sculpture and travel imagery can appear in an about page or a narrow editorial detail. Use actual project artifacts for the final portfolio; decorative/generated diagrams are not evidence. Write useful alt text; decorative imagery gets empty alt.

## Interaction and accessibility

180ms color/underline transitions. No mandatory entrance animation or parallax. Respect reduced motion. All links and controls receive a 2px focus outline with 5px offset. Minimum 44px control height. Normal text must reach WCAG AA 4.5:1; large text 3:1. Input boundaries and focus indicators should reach 3:1 against adjacent surfaces. Never communicate state by color alone. Verify keyboard order, zoom, contrast and responsive layouts when integrating components.

## Implementation

Reusable tokens and primitives: src/styles/stone-gallery.css. Review route: /design-system/. Styles are scoped to .stone-gallery so the current portfolio remains intact while this system is reviewed. Replace the old global theme only as part of the subsequent site redesign. Keep real biography and project content authoritative.
