# Modern UI Style Intelligence

Purpose: this file treats modern visual styles as fit-and-risk decisions, so an agent picks a style that suits the product, the user, and the trust stakes, and knows exactly where each style breaks.

## Rules that override every style

These rules sit above any individual style. When a style conflicts with a rule here, the rule wins.

- Style is chosen after product, user, and trust context are understood, never before.
- Text contrast and readability outrank visual trendiness, always.
- Modern effects must support clarity; an effect that costs readability is removed, no matter how current it looks.
- Trust-sensitive categories (healthcare, finance, banking, insurance, legal, government, serious B2B) get restrained styles.
- One statement style per product, applied on a neutral base; stacking two statement styles reads as noise.
- Motion and blur are performance budgets, not free decoration; mid-range phones are the baseline device.
- Dark backgrounds are not automatically premium; contrast discipline makes them premium.
- Every style must state a fallback for reduced motion and reduced transparency preferences.

A note on standards used throughout this file: body text needs 4.5:1 contrast, large text and UI components need 3:1 (WCAG 2.2 AA). Touch targets have a 44px practical minimum. Body text on mobile stays at 16px minimum. Honor prefers-reduced-motion and prefers-reduced-transparency. Where an effect can flash, respect the three-flashes limit (WCAG 2.3.1).

## How to choose

Five inputs decide the style. Read all five before naming a look, and write down what each one says, so the final choice can be explained rather than defended on taste.

- Product category and trust stakes: the more a wrong decision harms the user (money, health, legal standing), the more restrained the style. Trust-sensitive categories default to Swiss Modernism or Editorial Minimalism.
- Audience and age range: children tolerate playful depth and bright color; older or mixed audiences need larger text, higher contrast, and calmer motion.
- Content density: dense dashboards and tables reject decorative surfaces; sparse marketing and onboarding screens can carry a statement style.
- Performance budget and device mix: blur, mesh gradients, and animation cost GPU and battery. If mid-range phones are common, cut the heaviest effects first.
- Brand maturity: an established brand can hold restraint; a new brand may need one memorable style to be distinct, applied on a neutral base.

Mode 9 in [modes.md](./modes.md) runs this decision as a structured pass, so the selection is repeatable rather than taste-driven. When the five inputs disagree, trust stakes win: a high-stakes category pulls toward restraint even if the audience is young or the brand wants to stand out.

A short way to weigh the inputs: score trust stakes and content density first, because they set the ceiling on how expressive the style can be. Then let audience, performance budget, and brand maturity choose among the styles that remain. If the scoring notes matter to the wider review, see [scoring-rubric.md](./scoring-rubric.md).

## Selection matrix

This table maps product categories to styles that usually fit and styles to avoid. Treat it as a starting point, not a rule; the five inputs above can move a product.

| Product category | Styles that usually fit | Styles to avoid |
| --- | --- | --- |
| Healthcare and medical | Swiss Modernism, Editorial Minimalism, restrained Dark Premium SaaS | Neubrutalism, Cyberpunk UI, Claymorphism, heavy Glassmorphism |
| Banking and insurance | Swiss Modernism, High-Tech Fintech, Editorial Minimalism | Cyberpunk UI, Neubrutalism, Soft UI, Aurora UI as primary |
| Consumer fintech | High-Tech Fintech, Dark Premium SaaS, Bento Grid | Cyberpunk UI, Claymorphism, Soft UI for controls |
| Legal and government | Swiss Modernism, Editorial Minimalism | Glassmorphism, Neubrutalism, Cyberpunk UI, Aurora UI |
| B2B SaaS operations tools | Dark Premium SaaS, Swiss Modernism, Bento Grid | Claymorphism, Soft UI, Cyberpunk UI, Tactile Digital UI |
| Developer tools | Dark Premium SaaS, Swiss Modernism, High-Tech Fintech | Claymorphism, Soft UI, Organic Biophilic UI |
| AI products and copilots | AI-Native UI, Dark Premium SaaS, Bento Grid | Cyberpunk UI, Neubrutalism, Soft UI |
| Ecommerce (general) | Bento Grid, Editorial Minimalism, Gradient Mesh UI | Cyberpunk UI, Soft UI, Spatial UI |
| Luxury ecommerce | Luxury Minimalism, Editorial Minimalism, Mobile Cinematic Dark | Neubrutalism, Claymorphism, Cyberpunk UI, Soft UI |
| Local services and small business | Editorial Minimalism, Bento Grid, Swiss Modernism | Cyberpunk UI, Spatial UI, Liquid Glass |
| Education and children | Claymorphism, Tactile Digital UI, Bento Grid | Cyberpunk UI, High-Tech Fintech, Luxury Minimalism |
| Gaming and entertainment | Cyberpunk UI, Mobile Cinematic Dark, Aurora UI | Swiss Modernism as a brand look, Soft UI for controls |
| Wellness and sustainability | Organic Biophilic UI, Aurora UI, Editorial Minimalism | Cyberpunk UI, Neubrutalism, High-Tech Fintech |
| Media and editorial | Editorial Minimalism, Swiss Modernism, Bento Grid | Claymorphism, Soft UI, Cyberpunk UI |
| Portfolio and creative | Bento Grid, Aurora UI, Gradient Mesh UI, Neubrutalism | none inherently barred; match the maker's own voice |
| Consumer mobile lifestyle | Tactile Digital UI, Mobile Cinematic Dark, Gradient Mesh UI | High-Tech Fintech, Swiss Modernism as sole look |

The nineteen styles below each follow the same fields, so an agent can compare them on equal terms: what the style is, where it fits, where it fails, its accessibility, performance, and trust risks, concrete component examples with a note on what should not get the treatment, and CSS-level implementation notes with fallbacks. Read the risk fields as hard limits, not warnings to soften.

## Glassmorphism

**What it is:** Translucent surfaces that blur what sits behind them, giving a layered, frosted-panel feel with subtle borders and depth.

**Best use cases:** Marketing heroes, media overlays, music and photo apps, dashboard cards floating over an image or gradient backdrop.

**Where to use it:** Navigation bars over rich backgrounds, modal overlays, notification cards, and short stat panels where the blur reads as depth rather than clutter.

**Where not to use it:** Long-form reading, dense tables, primary form fields, and any trust-sensitive category where clarity must never be in doubt.

**Accessibility risks:** Text over glass loses contrast as the background changes; a scrolling backdrop makes the same text pass and fail. Users who set prefers-reduced-transparency expect the frost to drop away.

**Performance risks:** backdrop-filter blur is GPU-costly. Stacked or animated blur layers stutter on mid-range phones, and blur over video is the worst case.

**Trust risks:** In healthcare, finance, and legal contexts the drifting, semi-see-through look reads as unstable. It suggests style over substance where users want certainty.

**Component examples:** A translucent nav bar over a hero image; frosted modal overlays that dim and blur the page behind; a stat card cluster that floats above a colored backdrop; a media control bar over artwork. Body text panels, data tables, and form inputs should NOT get the treatment; put text on a solid surface.

**Implementation notes:** Apply `backdrop-filter: blur(12px)` with a semi-opaque background tint and a hairline border. Gate the effect behind `@supports (backdrop-filter: blur(1px))` and give a solid or semi-opaque fallback. Under `@media (prefers-reduced-transparency: reduce)` set the surface to a solid color and remove the blur. Add a scrim or raise text weight and contrast so text meets 4.5:1 against the darkest area of the moving background. Cap the number of simultaneous blurred layers.

## Liquid Glass

**What it is:** A richer glass treatment that adds refraction, edge distortion, and specular highlights, so panels behave like a physical lens; a term popularized by recent operating system releases.

**Best use cases:** Flagship consumer surfaces, launch screens, and hero moments where a single premium panel earns the cost.

**Where to use it:** A primary floating control cluster, a hero overlay, or a featured card, used once per screen as the focal surface.

**Where not to use it:** Text-heavy pages, dense tools, low-power contexts, and any product where the effect must run on every card at once.

**Accessibility risks:** Refraction and highlights push text contrast around even more than flat glass. The specular sheen can create moving bright edges that distract and reduce legibility.

**Performance risks:** Heavier than flat glassmorphism because refraction and highlights add passes. Animated liquid glass is the most likely single effect to drop frames on mid-range phones.

**Trust risks:** Same as glass, amplified. The showy optics read as marketing polish, which undercuts serious categories that need to feel dependable and plain.

**Component examples:** A single hero control bar with lensing edges; a featured product panel with a soft specular highlight; a floating action cluster that refracts the backdrop; a launch overlay. Never apply liquid glass to lists, tables, or body text containers; keep it to one focal surface.

**Implementation notes:** Layer a blurred backdrop, a subtle gradient border for the specular edge, and a small displacement or highlight overlay. Guard the whole effect with `@supports` and provide a flat, semi-opaque fallback panel. Under reduced-transparency, fall back to the same solid surface as glassmorphism. Under `prefers-reduced-motion` disable any animated highlight or lens movement. Test the focal text against the worst-case backdrop for 4.5:1.

## Bento Grid

**What it is:** A modular layout of boxed cells of varied sizes, arranged like a compartment tray, used to present features or metrics as a scannable set.

**Best use cases:** Feature overviews, product landing pages, dashboards, and summary screens that group many small ideas.

**Where to use it:** Marketing pages, home dashboards, pricing and feature comparisons, and portfolio index screens.

**Where not to use it:** Single linear tasks, step-by-step flows, and long reading, where a grid fragments a story that should stay continuous.

**Accessibility risks:** Reading order can break if the visual grid and the source order disagree. Cells with different backgrounds can each fail contrast in their own way, so each cell needs its own check.

**Performance risks:** Low in plain form. Risk rises only when cells carry heavy media, blur, or animation, so budget those per cell.

**Trust risks:** Low. The main failure is a marketing feel where a serious tool needs a workspace feel, so tone the cells down for operations products.

**Component examples:** One hero cell for the headline metric or primary feature; smaller cells for secondary metrics; a media cell; a call-to-action cell. Do NOT make every cell the same weight; a flat grid with equal cells kills hierarchy and reads as a wall.

**Implementation notes:** Use CSS grid with `grid-template-columns` and `grid-column` or `grid-row` spans to size cells. The trap is uniform visual weight across cells, which kills hierarchy; define one hero cell that is larger or higher contrast. Plan the linearized mobile order deliberately: set the source order to match the priority you want on a single column, and test that the screen reader path and the visual path agree. Avoid reordering cells only with visual grid placement, since that leaves the reading order stuck in source order and confuses assistive tech. Keep gaps consistent and give each cell enough internal padding that its content does not crowd the cell edge.

## Dark Premium SaaS

**What it is:** A dark interface built on near-black surfaces with restrained accents and layered elevation, aiming for a calm, focused, professional feel.

**Best use cases:** Developer tools, analytics, operations dashboards, and B2B products used for long sessions.

**Where to use it:** Workspaces, data views, settings, and any product where users spend hours and want low glare.

**Where not to use it:** Content aimed at bright-environment reading, print-like documents, and audiences who prefer light interfaces by default; offer a light theme too.

**Accessibility risks:** Pure white text on pure black causes halation and eye strain. Low-contrast gray-on-gray secondary text is a common failure, so 4.5:1 still applies to every text tier.

**Performance risks:** Low. Glow and shadow effects add minor cost; the real risk is overusing glow, which muddies the surface hierarchy.

**Trust risks:** Low when disciplined. Excess neon glow or saturated accents can tip a serious tool toward a gaming look, so keep accents desaturated.

**Component examples:** A sidebar with lighter-surface active state; data cards raised by a lighter background step; a top bar with a single accent action; charts with desaturated series colors. Do NOT rely on glow to signal state; use surface steps and clear labels.

**Implementation notes:** Use near-black surfaces (not pure black next to pure white text); a soft white in the `#E6E6E6` range on a base in the `#0B0D12` range reduces halation. Build elevation via lighter surface steps instead of heavy shadows, for example a base surface, a raised surface, and a top surface each a few points lighter. Keep accents desaturated and use glow sparingly. Confirm 4.5:1 for every text tier, including muted secondary text, and 3:1 for controls and chart strokes. Define the surface steps as tokens so elevation stays consistent across the product, and reserve the single accent color for the primary action and active states, not for decoration. Test the theme in a bright room, since dark themes that look calm in the dark can lose readable contrast in daylight.

## AI-Native UI

**What it is:** An interface pattern for assistants and copilots built around live generation, so the product shows its thinking, its sources, and its controls rather than hiding them.

**Best use cases:** Chat assistants, copilots inside tools, search and answer products, and any feature that generates content on the fly.

**Where to use it:** Response streams, prompt areas, inline suggestions, and result panels that need provenance and correction controls.

**Where not to use it:** As a decorative theme on non-AI features; the sparkle look without real AI behavior reads as hollow.

**Accessibility risks:** Streaming text can fight screen readers if updates fire on every token; announce complete chunks, not each character. Thinking animations need a reduced-motion fallback.

**Performance risks:** Frequent DOM updates during streaming can thrash layout. Batch tokens and avoid reflowing the whole page on each update.

**Trust risks:** The purple-gradient sparkle cliche implies capability the model may not have. Trust comes from showing sources and states, not sparkle iconography, so overpromising visuals are the main risk.

**Component examples:** A streaming response with a visible thinking or generating state; a citation and provenance affordance on each claim; undo and regenerate controls near the output; a stop-generating control. Do NOT bury the source and state cues; they are the trust surface.

**Implementation notes:** Show streaming and thinking states as explicit, labeled UI, not just a spinner. Attach citation and provenance affordances to generated claims so users can verify. Provide undo and regenerate controls in reach of the output. Show restraint about the purple-gradient cliche and use a neutral base. Under `prefers-reduced-motion` replace typing and pulsing animations with a static in-progress label. Ensure live regions announce settled chunks for assistive tech.

## Neubrutalism

**What it is:** A raw, high-contrast style with thick black borders, hard offset shadows, unrounded corners, and saturated flat color, deliberately unpolished.

**Best use cases:** Creative portfolios, bold marketing pages, event sites, and youth-facing brands that want to stand out.

**Where to use it:** Landing pages, campaign microsites, and playful product marketing where personality beats calm.

**Where not to use it:** Trust-sensitive categories and any long-session tool; the loud contrast fatigues users over time.

**Accessibility risks:** Strong contrast helps scanability, which is a genuine plus, but the same intensity fatigues long sessions and can overwhelm users sensitive to visual noise. Check that saturated color pairs still meet contrast.

**Performance risks:** Very low. Flat color, hard shadows, and simple borders are cheap to render.

**Trust risks:** High in serious sectors. The intentionally rough look signals informality, which reads as careless where users want competence and care.

**Component examples:** Buttons with a hard offset shadow and thick border; cards with unrounded corners and flat fills; tags in saturated blocks; a bold headline band. Do NOT use it on dense financial tables or medical data, where the loud frame competes with the content.

**Implementation notes:** Use `border: 3px solid` in a near-black, `box-shadow` with no blur for the hard offset, and `border-radius: 0`. Keep saturated fills, but verify each text-on-fill pair meets 4.5:1 and each control edge meets 3:1. There is little motion to manage, but if hover shifts the shadow, keep the movement small and disable it under `prefers-reduced-motion`. Limit the number of loud elements per screen so hierarchy survives.

## Claymorphism

**What it is:** Soft, inflated 3D shapes with rounded edges and paired inner and outer shadows, giving a friendly, toy-like, tactile feel.

**Best use cases:** Children's apps, education products, playful onboarding, and light consumer features.

**Where to use it:** Illustrative sections, onboarding cards, empty states, and reward or achievement moments.

**Where not to use it:** Trust-sensitive categories, dense tools, and anywhere the soft blobs blur the line between decoration and control.

**Accessibility risks:** The inflated shapes can hide whether something is a button or an image, a control affordance risk. Soft edges against soft backgrounds create a 3:1 non-text contrast risk for the control boundary.

**Performance risks:** Low to moderate. Multiple layered shadows on many elements add paint cost, so keep the count modest on mobile lists.

**Trust risks:** High in serious sectors. The playful, childlike surface undercuts authority in finance, health, and legal contexts.

**Component examples:** Inflated icon tiles on an onboarding screen; a soft reward badge; playful category cards; a friendly toggle. Do NOT rely on the clay look alone to mark interactivity; add clear labels and a distinct pressed state.

**Implementation notes:** Combine an outer `box-shadow` and an inner shadow with a generous `border-radius` for the inflated look. Ensure control boundaries meet 3:1 against the background so the shape reads as a control, and pair the visual with a text label. Provide a clear pressed and focus state. Under `prefers-reduced-motion` keep any squish animation off. Limit layered shadows per view to protect paint performance on mobile.

## Soft UI

**What it is:** A descendant of neumorphism where elements look extruded from the same background using twin light and dark shadows, so surfaces feel embossed rather than layered.

**Best use cases:** Decorative accents, single hero controls, and low-stakes concept screens where the effect is contained.

**Where to use it:** A featured toggle, a single dial, or a small accent panel, kept away from primary task flows.

**Where not to use it:** Primary controls, forms, dense interfaces, and trust-sensitive categories; the affordance and contrast problems are severe.

**Accessibility risks:** Severe. Same-color extruded controls have very low edge contrast, often failing 3:1, and users cannot tell what is pressable. This is the style's defining weakness.

**Performance risks:** Low. Twin shadows are cheap; the problem is usability, not speed.

**Trust risks:** Moderate to high. The trend look dated quickly and its unclear controls erode confidence in serious products.

**Component examples:** A single decorative toggle; an accent stat tile; a soft search field used sparingly; a hero dial. Do NOT build a whole form or navigation from Soft UI; use decorative accents, not primary controls.

**Implementation notes:** Use a light-source `box-shadow` pair (one light, one dark) on a surface that matches the background. Because edges are faint, add an explicit border or a distinct focus and active state so the control meets 3:1 and is clearly operable. Keep it to accents, not primary paths. There is little motion; ensure any press animation respects `prefers-reduced-motion`. If contrast cannot reach 3:1, drop the extruded look for a solid surface.

## Spatial UI

**What it is:** Depth-layered, semi-translucent panels arranged in 3D space for headset, AR, and 3D-adjacent products, where content floats at different depths.

**Best use cases:** AR and VR apps, immersive product demos, and 3D configurators.

**Where to use it:** Spatial home layouts, floating panels in a scene, and depth-based navigation in headset contexts.

**Where not to use it:** Dense 2D information work, where depth adds cost without clarity; most desktop dashboards are the wrong home for it.

**Accessibility risks:** Targets must be larger because pointing in space is less precise, so the 44px minimum grows. Parallax and depth motion carry a motion-sickness risk that a reduced-motion setting must fully address.

**Performance risks:** High. Real-time depth, translucency, and motion are demanding, and dropped frames in a headset are worse than on a screen.

**Trust risks:** Low in its native context, but out of place on a flat business tool where it looks like novelty for its own sake.

**Component examples:** Floating panels at varied depths; a spatial menu that arcs around the user; depth-cued cards; a grabbable control surface. Do NOT force dense tables or long forms into floating spatial panels; keep detailed 2D work flat.

**Implementation notes:** In platform-neutral terms, layer panels with clear depth cues, enlarge targets beyond the flat 44px minimum, and keep translucency light enough that text stays at 4.5:1. Provide a strong `prefers-reduced-motion` path that removes parallax and depth animation, since motion sickness is the key harm. Reserve the style for genuinely spatial products; on a flat screen prefer a layered flat layout instead.

## Aurora UI

**What it is:** Soft, drifting washes of color that blend like northern lights across a background, giving a calm, atmospheric, modern mood.

**Best use cases:** Marketing heroes, wellness and lifestyle apps, launch pages, and empty states that want atmosphere.

**Where to use it:** Hero backgrounds, section dividers, sign-in screens, and ambient backdrops behind sparse content.

**Where not to use it:** Behind dense text or data, and in trust-sensitive categories where a moving color field feels unserious.

**Accessibility risks:** Text over the wash shifts contrast as colors move, so text needs a solid or scrimmed zone. The slow motion must stop under `prefers-reduced-motion`.

**Performance risks:** Moderate. Animated gradients and large blurred color fields cost GPU, and cheap displays show banding across smooth transitions.

**Trust risks:** Moderate. The ambient look suits wellness and lifestyle but signals mood over rigor in finance, legal, and medical products.

**Component examples:** A hero background wash; a sign-in panel over a soft aurora; a section divider with drifting color; an ambient empty state. Do NOT place body copy or tables directly on the moving field; give them a solid zone.

**Implementation notes:** Build the wash from layered `radial-gradient` color stops with heavy blur, animated slowly if at all. Consider static gradients with a long animation disabled under reduced motion, so the default respects the setting. Add dithering or noise to reduce banding on cheap displays. Place text on a solid or scrimmed area that holds 4.5:1 regardless of the wash beneath it. Keep the animated area small to protect performance.

## Editorial Minimalism

**What it is:** A content-led style with a strong type scale, a disciplined grid, hairline rules, and generous whitespace, so words and images lead and chrome recedes.

**Best use cases:** Media, documentation, marketing for serious products, and any content-first experience.

**Where to use it:** Articles, landing pages, docs, and case studies where reading is the point.

**Where not to use it:** Dense interactive tools that need visible controls; the quiet chrome can hide the interface.

**Accessibility risks:** The main risk is under-signposted interactivity: links and buttons styled too subtly become invisible. Ensure interactive elements have clear affordance and focus states.

**Performance risks:** Very low. The style leans on type and space, which are cheap.

**Trust risks:** Low, and often positive. Restraint reads as credible, which is why it suits serious content.

**Component examples:** A large headline with a measured subhead; body columns at a comfortable measure; hairline dividers between sections; a quiet but visible link style. Do NOT let primary actions blend into text; give buttons a clear, testable state.

**Implementation notes:** Set a deliberate type scale and a consistent baseline rhythm, keep line length near 60 to 75 characters, and use hairline `border` rules for structure. Make interactive elements obviously interactive: a distinct link color meeting 4.5:1, an underline or clear button shape, and a visible focus ring. Body text stays at 16px minimum on mobile. Motion is minimal; any of it respects `prefers-reduced-motion`. Let whitespace carry the grouping so you can drop most boxes and dividers, but keep enough structure that scanning users still find the sections. Do not rely on hover alone to reveal actions, since touch and keyboard users never see hover.

## Luxury Minimalism

**What it is:** Extreme restraint built on wide-tracked uppercase labels, a muted palette, large imagery, and slow, subtle motion, aiming for a refined, high-end feel.

**Best use cases:** Luxury retail, premium brands, high-end services, and flagship product pages.

**Where to use it:** Brand and product pages, lookbooks, and landing experiences where mood carries value.

**Where not to use it:** Dense functional tools and any product where small, quiet text would hide critical information.

**Accessibility risks:** The small-low-contrast-text temptation is the main accessibility risk: refined often means tiny and faint. Wide letter-spacing on long text also hurts reading speed.

**Performance risks:** Low to moderate. Large imagery is the main cost, so serve responsive, compressed images.

**Trust risks:** Low in retail and brand contexts. It would feel evasive in finance or legal, where plainness signals honesty.

**Component examples:** A wide-tracked uppercase nav; a full-width image with a restrained caption; a slim call-to-action; a slow fade on scroll. Do NOT shrink prices, terms, or key details into faint small text; keep decisive information legible.

**Implementation notes:** Use `letter-spacing` on short uppercase labels only, not on body copy. Resist the pull toward tiny faint type: body text stays 16px minimum on mobile and every text tier meets 4.5:1. Serve large imagery as responsive, compressed assets. Keep motion slow and subtle, and disable it under `prefers-reduced-motion`. If a refined color pair fails contrast, darken or lighten it until it passes; the standard is not optional.

## Cyberpunk UI

**What it is:** A high-energy dark style with neon accents, glitch and scanline motifs, and a tech-noir mood, built for spectacle.

**Best use cases:** Games, entertainment, music events, and youth entertainment brands.

**Where to use it:** Game menus, launch pages for entertainment, and event microsites.

**Where not to use it:** Any serious category; the look causes instant trust loss in finance, health, legal, and government.

**Accessibility risks:** Neon on dark often fails contrast for text, and glitch effects can flash. Where flashing is possible, respect the three-flashes rule (WCAG 2.3.1) so no sequence flashes more than three times per second.

**Performance risks:** Moderate to high. Glitch, scanline, and glow animations run constantly and can drain battery and drop frames.

**Trust risks:** Very high outside entertainment. The style reads as fiction, so it destroys credibility where users are making real decisions with money or health.

**Component examples:** A neon-outlined menu; a glitching title treatment; scanline overlays on panels; a glowing primary action. Do NOT use glitch or flash on anything a user must read or on error and payment states.

**Implementation notes:** Keep neon accents off body text; put readable copy on solid dark surfaces meeting 4.5:1. Any glitch or flash animation must stay under three flashes per second and stop entirely under `prefers-reduced-motion`. Use glow sparingly to avoid halation and battery drain. Confine the style to entertainment surfaces; never carry it into account, payment, or legal flows.

## High-Tech Fintech

**What it is:** A dense, precise data style with tabular figures, micro-charts, tight spacing, and a controlled palette, built to signal competence and rigor.

**Best use cases:** Trading, analytics, treasury, and professional finance tools for informed users.

**Where to use it:** Data-heavy dashboards, portfolio views, and reporting screens for users who read numbers all day.

**Where not to use it:** Beginner-facing consumer finance, where the density intimidates and the precision overwhelms.

**Accessibility risks:** Dense figures at small sizes strain reading; keep numeric text at a legible size and 4.5:1. Color-only encoding of gain and loss fails colorblind users, so pair color with sign or shape.

**Performance risks:** Moderate. Many live micro-charts and frequent data updates cost render time; virtualize long tables and throttle updates.

**Trust risks:** The risk is false precision and intimidating novice users. Showing many decimals or busy charts can imply certainty the data lacks, and can scare newcomers away.

**Component examples:** Numeric tables using tabular figures; inline sparkline micro-charts; a tight metric header row; a precise change indicator with sign and color. Do NOT encode gain and loss by color alone; include a sign or arrow.

**Implementation notes:** Use `font-variant-numeric: tabular-nums` so digits align in columns. Keep spacing precise and consistent, and virtualize long tables for performance. Pair any color encoding with a sign or shape for colorblind users. Keep numeric body text at a legible size meeting 4.5:1. Round to a sensible precision to avoid false precision. For novice-facing views, reduce density and add plain-language labels.

## Mobile Cinematic Dark

**What it is:** A mobile-first style built on full-bleed imagery or video, dark scrims, large type, and bottom-anchored actions, for an immersive, filmic feel.

**Best use cases:** Streaming, travel, events, and lifestyle apps where media is the hero.

**Where to use it:** Onboarding, detail and hero screens, and media browsing on phones.

**Where not to use it:** Data-dense mobile tools and low-bandwidth contexts where heavy media is a burden.

**Accessibility risks:** Text over imagery needs a reliable scrim so it holds 4.5:1 across every frame, including bright ones. Bottom actions must respect safe areas and stay within thumb reach.

**Performance risks:** High on data and battery. Full-screen video and large images cost bandwidth and power, so lazy-load and cap autoplay.

**Trust risks:** Low in media and lifestyle. It would feel style-first in finance or health, where clarity beats atmosphere.

**Component examples:** A full-bleed hero image with a gradient scrim; a bottom-anchored primary action within thumb reach; large title type over media; a swipeable media carousel. Do NOT place fine print or dense controls over busy imagery.

**Implementation notes:** Lay a gradient scrim between media and text so contrast holds at 4.5:1 against the brightest frame. Anchor primary actions to the bottom within thumb reach and honor device safe-area insets. Lazy-load media, compress aggressively, and avoid autoplaying video on cellular. Under `prefers-reduced-motion` do not autoplay video and remove parallax. Keep body text at 16px minimum.

## Swiss Modernism

**What it is:** A grid-disciplined style with objective sans typography, flat color, strong alignment, and no ornament, built for clarity and neutrality.

**Best use cases:** Serious B2B, government, documentation, and any product where trust and legibility lead.

**Where to use it:** Enterprise tools, public-sector services, docs, and reference interfaces; it is the reliable default for serious work.

**Where not to use it:** Places that need a distinct personality to stand out, where pure neutrality can feel plain.

**Accessibility risks:** Low. The main watch item is that flat color still meets contrast and that focus states stay visible against the clean surfaces.

**Performance risks:** Very low. Flat color, type, and grid are inexpensive to render.

**Trust risks:** Low, and usually positive. The risk is feeling generic when spacing rhythm is lazy, so the neutrality reads as unfinished rather than considered.

**Component examples:** A strict column grid; an objective sans type scale; flat buttons with clear states; aligned data labels and values. Do NOT let inconsistent spacing creep in; the rhythm is what separates considered from generic.

**Implementation notes:** Define a spacing scale and hold to it, since consistent rhythm is what makes the neutrality read as deliberate. Use a single objective sans family with a clear scale. Keep flat colors that meet 4.5:1 for text and 3:1 for controls, and keep focus rings visible on clean backgrounds. Motion is minimal by design; any of it respects `prefers-reduced-motion`. Alignment and grid discipline do the work that ornament would elsewhere. When the layout feels generic, the fix is almost always tighter alignment and a truer spacing rhythm, not added decoration. This style also degrades gracefully: with color and images stripped, the grid and type still communicate, which is why it suits documentation and public services.

## Organic Biophilic UI

**What it is:** A nature-led style using earthy palettes, soft organic shapes, and nature imagery and texture, aiming for calm and a connection to the natural world.

**Best use cases:** Wellness, sustainability, outdoor, and food and wellbeing brands.

**Where to use it:** Marketing, onboarding, and content screens where a natural, calm tone fits the mission.

**Where not to use it:** High-density tools and categories where a soft natural look would seem to soften serious information.

**Accessibility risks:** Earthy low-contrast palettes can fail text contrast, so verify muted greens and browns against text at 4.5:1. Textured backgrounds behind text reduce legibility.

**Performance risks:** Low to moderate. Nature photography and texture assets add weight, so compress and serve responsive images.

**Trust risks:** The trust risk is if the brand's actual practices do not support the natural positioning. A green look on a product with no real sustainability substance reads as greenwashing.

**Component examples:** Soft organic-shaped cards; a natural-texture section background; nature imagery in heroes; earthy category tiles. Do NOT place body text on a busy natural texture; keep text on a solid, sufficiently contrasted panel.

**Implementation notes:** Use organic shapes via `border-radius` variation and soft clip paths, and keep texture behind decorative areas, not text. Verify earthy palette pairs meet 4.5:1 for text and 3:1 for controls. Compress nature imagery and serve responsive sizes. Keep motion gentle and honor `prefers-reduced-motion`. Match the visual claim to real practice, since the credibility risk here is substance, not code.

## Tactile Digital UI

**What it is:** A playful style built on pressable, squishy components, springy motion, and haptic pairing on device, so controls feel physical and responsive.

**Best use cases:** Consumer mobile lifestyle apps, games-adjacent products, and playful onboarding.

**Where to use it:** Buttons, toggles, sliders, and micro-interactions on phones where a physical feel adds delight.

**Where not to use it:** Serious tools and trust-sensitive categories, and any context where motion cannot be a budget item.

**Accessibility risks:** Springy motion can trigger discomfort, so reduced-motion fallbacks are mandatory and must remove the spring entirely. Haptics need a setting to disable them.

**Performance risks:** Moderate. Spring animations on many elements cost frames on mid-range phones, so limit concurrent animations.

**Trust risks:** Moderate to high in serious sectors. The toy-like feel undercuts authority where users want a calm, businesslike surface.

**Component examples:** A button that compresses on press; a toggle with a springy snap; a slider with tactile detents; a pull-to-refresh with a physical rebound. Do NOT attach bouncy motion to error, payment, or confirmation states that should feel steady.

**Implementation notes:** Use spring-style transitions on `transform` for press feedback, and pair with device haptics where available and user-enabled. Motion restraint and reduced-motion fallbacks are mandatory: under `prefers-reduced-motion` replace springs with instant or short linear state changes. Limit the number of simultaneous spring animations to protect frame rate. Keep targets at 44px minimum and ensure pressed states are also visible, not only felt.

## Gradient Mesh UI

**What it is:** A style built on multi-point color fields that blend smoothly across large areas, used as heroes and section backgrounds for a modern, colorful mood.

**Best use cases:** Marketing pages, product launches, portfolios, and consumer apps that want color as identity.

**Where to use it:** Hero backgrounds, section backdrops, and feature cards where color leads and text sits in a safe zone.

**Where not to use it:** Behind dense text or data, and in trust-sensitive categories where a colorful field feels unserious.

**Accessibility risks:** Text over a mesh shifts contrast across the field, so text needs solid or scrimmed zones holding 4.5:1. Bright mesh fields can also strain the eye behind reading content.

**Performance risks:** Moderate. Exported mesh images cost weight while CSS approximations are cheaper; large image meshes hurt load time on mobile.

**Trust risks:** Moderate. The look suits consumer and creative brands but signals marketing over rigor in serious categories.

**Component examples:** A hero mesh background; a section backdrop with a text-safe zone; a feature card with a soft mesh fill; a mesh divider. Do NOT set body copy or tables directly on the color field; give them a solid or scrimmed area.

**Implementation notes:** Prefer CSS approximations using several layered `radial-gradient` color points over exported mesh images, since the CSS route is cheaper on weight; reserve image meshes for cases the CSS cannot match. Add noise or dithering to reduce banding. Place text on solid or scrimmed zones that meet 4.5:1 regardless of the colors behind. If the mesh animates, keep it slow and disable it under `prefers-reduced-motion`.

## Trend risk and longevity

A style is a bet on how long a look stays credible. Treat that bet as a cost.

- Statement styles date faster than restrained ones. The louder the look, the sooner it reads as of-its-moment, so weigh a restyle cost into the choice.
- Restraint ages slowly. Grid discipline, clear type, and honest contrast look current for years, which is part of why serious categories default to them.
- Separate the durable layer from the fashionable layer. Keep structure, hierarchy, and readability stable, and let the expressive surface carry the trend, so a future refresh touches the surface, not the foundation.
- Do not adopt a look only because it is new. Novelty is not a user need, and a style with no fit reason is a liability the next redesign has to pay off.

## Combining styles

Mixing styles is where products turn to noise. A few rules keep a mix coherent.

- Use a neutral base plus one statement style; the base carries most surfaces and the statement style appears in a few focal places.
- Share one radius scale and one spacing scale across the whole mix, so components from different influences still feel related.
- Keep typography constant; do not change the type family or scale per section, since that is the fastest way to look assembled from parts.
- If two statement styles both want the spotlight, cut one; two loud looks compete and cancel.
- Let the statement style live mostly in marketing and hero surfaces, and let the neutral base run the functional core, so the working screens stay calm.
- Keep the same interaction rules everywhere: a button behaves and looks like a button across the whole product, regardless of which surface it sits on.
- When in doubt, remove the second flourish; a coherent product with one clear voice beats a busy one with two.

## Adopting a style on an existing product

Restyling a live product is a migration, not a repaint. Sequence it to protect users.

- Tokens first: define color, type, spacing, and radius tokens for the new style before touching screens, so the change is centralized and reversible.
- Pilot one surface: apply the style to a single screen or component group, gather feedback, and confirm it holds up before rolling wider.
- Re-check contrast after restyle: a new palette can quietly break 4.5:1 and 3:1, so audit every text and control state again on the restyled surface.
- Re-check reduced-motion and reduced-transparency paths after the restyle, since a new style can introduce effects the old fallbacks never covered.
- Do not restyle and restructure in the same release: changing the look and the layout or flow at once makes regressions hard to trace and hard to roll back.
- Keep the old and new styles from mixing mid-flow: ship the restyle by whole screens or whole components, so a single task never shows two looks at once.

## Universal checks before shipping any style

Whatever style wins, these checks apply. They are the floor, not the finish line.

- Every text tier meets 4.5:1, and large text, controls, and meaningful graphics meet 3:1.
- Touch targets are at least 44px, and interactive elements have a visible focus state for keyboard users.
- Body text on mobile is at least 16px, and reading order matches visual order.
- Motion has a reduced-motion fallback, transparency has a reduced-transparency fallback, and nothing flashes more than three times per second.
- The look holds on a mid-range phone at the target device mix, not only on the design machine.
- Meaning never rides on color alone; state and status also carry a label, an icon, or a shape.
