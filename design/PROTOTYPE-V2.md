# Shubh Vastu AI Astro — prototype V2

Open `ui-prototype.html` directly in a browser. It remains a standalone HTML/CSS/JavaScript prototype with no runtime dependencies, build step, React, or Ant Design installation.

## Design changes

- Replaced the original styles and later overrides with one component-grouped stylesheet. Central tokens define the supplied navy, blue, teal, white, background, text and border palette, along with control height, spacing and radius. Teal uses a darker companion for small text; bright teal is reserved for focus and decorative accents.
- Refined the fixed navy sidebar, compact white header and mobile bottom navigation. Content uses a consistent maximum width, responsive grids and safe-area padding.
- Kept the navy hero and geometric identity, with a charcoal primary action and white secondary action. Service rows use a 76px desktop minimum height and expand for translated copy.
- Added explicit remaining trial balances (3/3 questions, 1/1 chart), accessible meters and unchanged allowance explanations. Consultancy remains separate from AI plans.
- Improved all seven views with shared controls, restrained cards, consistent spacing and responsive pricing. Prices remain Free ₹0, Basic ₹49, Standard ₹149 and Premium ₹349, with all original allowances and validity unchanged.
- Retained every original Marathi, Hindi and English translation verbatim. New interaction copy lives in a separate `UI` dictionary. Language switching and navigation preserve form drafts in memory; chat history also survives both.
- Added required markers, inline validation and future birth-date validation. Unknown birth time retains the original disabled-generation behavior and explanation. Loading is explicitly simulated, and results state that no calculation or quota use occurred.
- Chat includes a persistent AI-disconnected notice, speaker labels, suggested questions, empty-input disabling, simulated loading and an explicit unavailable/error response. User input is rendered as text, never HTML.
- Added skip navigation, route-heading focus, mobile current-page semantics, associated error descriptions, labelled modal, native Escape handling and reduced-motion support.

## Future component boundaries

| Prototype component / pattern | Responsibility | React / Ant Design implementation |
| --- | --- | --- |
| AppShell, AppSidebar, AppHeader | Layout, active route, language selection | Layout, Layout.Sider, Menu, Layout.Header, Select; React Router |
| MobileNavigation | Safe-area navigation, More routes | Custom navigation with Grid breakpoints and Router links |
| HeroSection | Brand introduction and two route actions | Semantic section, Typography, Button |
| ServiceRow | Reusable icon, title, description and route affordance | Custom ServiceRow with token styles |
| QuotaSummary | Remaining allowances and trial state | Card, Statistic, Tag, Progress |
| ConsultantCard, ContactProfile | Human service identity and contact channels | Card, Avatar, Typography, Button |
| AIChatPanel | Conversation state and service availability | Custom panel; Alert for service status |
| ChatMessage, ChatComposer | Safe message rendering, input and pending/error states | Custom ChatMessage, Form, Input, Button |
| BirthDetailsForm | Birth data, consent, unknown-time behavior and validation | Form, DatePicker, TimePicker, AutoComplete, Checkbox |
| VastuForm | Property, direction, room, layout and consent | Form, Select, Input.TextArea, Checkbox, Alert |
| PrashnaForm | Question context and pending-method explanation | Form, DatePicker, Input, Alert |
| PricingPlanCard | Plan comparison and selection | Card, Tag, Button; Modal for prototype confirmation |

Map CSS tokens to ConfigProvider `colorPrimary`, `colorText`, `colorTextSecondary`, `colorBorder`, `colorBgLayout`, `colorBgContainer`, `borderRadius` and `controlHeight`. Use component tokens for the navy menu and teal active indicator. Keep localization, form drafts, chat state and service adapters outside presentation components. `quotaMetrics`, `field`, `heading`, `btn` and `status` demonstrate reusable rendering boundaries.

## Production-only work

- Authenticated accounts, secure draft storage, retention/deletion policies and consent records.
- Place autocomplete, confirmed coordinates and timezone, historical timezone resolution, strict date/time validation and unknown-time calculation policy.
- A verified planetary-calculation adapter with provenance, separate from the AI interpretation service. Never synthesize planetary data with AI.
- Real AI integration, streaming, cancellation, retry policies, moderation and server-side quota accounting. Prototype timers only demonstrate UI states.
- Consultant-approved Vastu contracts and Prashna methodology; neither form currently generates recommendations.
- Payment provider integration, verified tax-inclusive prices, purchase terms and server-side entitlements. No checkout takes place here.
- Approved brand artwork, consultant identity assets, professional translation review and assistive-technology/device testing.

No form data leaves this file. Drafts and chat history clear on reload. Existing WhatsApp and telephone links remain real external contact links; QA does not activate them.

## Verification

Run `node design/qa-ui.cjs` using the existing local Playwright runtime and Chrome. The harness covers seven pages × three languages × five widths (360, 390, 768, 1024, 1440), document overflow, runtime errors, navigation, retained drafts, birth validation/loading, unknown time, chat text escaping/history/empty state/suggestions, Vastu validation and result state, Prashna draft retention and modal Escape handling. Screenshots are written to the existing preview and QA paths. Browser checks do not replace a production accessibility audit or verification of calculation services.

## Card refinement

Primary action buttons now use charcoal (#292D32), with white secondary buttons and charcoal labels. Cards use a shared 16px radius, soft neutral borders and restrained elevation. Pricing cards have aligned icon/title headers, larger prices, a single divider, quieter benefit rows and anchored actions. The recommended plan uses a charcoal outline and floating label rather than a blue top border. Prices, translations, allowances and interactions are unchanged. All 105 responsive page/language combinations and interaction checks passed again after this refinement.

## Homepage follow-up

The Namaskar hero now uses a subtle blue-to-white gradient with dark text. Get in touch and View plans use charcoal primary buttons. The homepage free-trial panel now groups trial status, two separate allowance cards and a dedicated action footer. Service icons, navigation active icons and service arrows use charcoal on light surfaces; sidebar icons remain light for contrast.

Google Material Symbols Rounded replace the interface glyphs. The requested font subset is embedded in the HTML to keep the file standalone and usable offline. Source: https://developers.google.com/fonts/docs/material_symbols. The Apache 2.0 license is retained in GOOGLE-ICONS-LICENSE.txt. Original decorative brand geometry remains intact. All 105 responsive combinations and existing interaction checks passed after these changes.

## AI Guruji focus mode

AI Guruji now occupies the full viewport with the desktop sidebar and mobile bottom navigation hidden. A persistent Home button restores the normal application shell. Language selection and a visible demo disclaimer remain available. The conversation scrolls independently above the persistent composer, while quota and calculation-context details expand within the conversation area. Existing birth-details and contact actions remain in that section. Drafts and messages survive entering and leaving focus mode. Responsive and interaction checks passed across all five widths and three languages; desktop and mobile screenshots were reviewed.

## Right navigation rail

Desktop navigation now uses a white 76px icon rail on the right. The arrow toggle expands it into a 260px labelled drawer; Escape collapses it. Labels remain accessible through aria-label and native tooltips in icon mode. Selected navigation uses charcoal with white content, and unselected items use charcoal on white. Mobile retains bottom navigation with the same selected colors. Guruji focus mode continues to hide navigation. Five-width/three-language checks and expand/collapse checks passed.

## Left rail placement correction

The navigation rail is now on the left, with the logo at the top and the expand/collapse control at the bottom. Expansion uses a 280ms eased width transition, fading labels and a rotating arrow; reduced-motion preferences disable animation. White/charcoal colors and Guruji focus mode are preserved. Responsive and drawer checks passed after the placement change.

## Floating Guruji entry and double chevrons

The navigation toggle now uses the embedded Google Material Symbols double-chevron icon, rotating between expand and collapse. A navy/white/orange gradient AI Guruji button floats at the lower right on desktop and above the safe-area bottom navigation on mobile. It uses the existing route action, retains translated labels and hides during Guruji focus mode. Extra bottom content spacing keeps final-page content reachable above the floating control.

## Gradient and hover-label refinement

The floating Guruji control now uses the supplied five-stop OKLCH blue-to-green gradient, with a conventional gradient fallback. Its dark icon remains visible; the translated label expands on hover or keyboard focus. Touch users can tap the icon directly. Guruji has been removed from desktop and mobile navigation; the floating button and homepage primary action remain entry points. Mobile bottom navigation now has four evenly spaced items.
