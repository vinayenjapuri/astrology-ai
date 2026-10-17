# Shubh Vastu Phase 1 design

- `Shubh-Vastu-System-Design.docx`: system design using the selected template, with architecture, security, data contracts, flows, UI requirements, rollout and commercial assumptions.
- `ui-prototype.html`: standalone interactive UI, default Marathi with Hindi and English. Open directly in a browser. No install or build step required.
- `architecture.png`: architecture diagram source asset.
- `ui-desktop.png` and `ui-mobile.png`: UI previews.

The prototype has no live authentication, calculations, AI or payments. Its forms show a clear unavailable state instead of fabricated results. The WhatsApp and telephone links use the supplied business contact. The geometric logo and initials are placeholders, not an approved identity or consultant photograph.

The proposed production stack is React, TypeScript, Vite, Ant Design, react-i18next, Firebase and AstrologyAPI. This standalone prototype establishes the visual and interaction design; it is not the production PWA or a Play Store application.

## Verification

Browser checks passed for seven screens, three languages and five widths (360, 390, 768, 1024, 1440). Checks covered document overflow, runtime errors, language changes preserving forms, missing birth time, safe text rendering and the plan selection modal. No external contact links were clicked.

The 10-page DOCX was rendered and visually reviewed. Template package parts were preserved except document content, the architecture image, the organization footer and the example footnote. The original reference file was not modified. QA records and generation scripts are included for reproducibility.

## Before implementation

Validate AstrologyAPI Marathi, calculation provenance, Vastu response contracts and Prashna methodology. Confirm client logo, tax and refund policy, support scope and domain. Pricing figures are planning estimates from the earlier discussion, not a fresh vendor quote. Paid PDFs and marriage matching remain out of Phase 1.

## Prototype V2

See [PROTOTYPE-V2.md](PROTOTYPE-V2.md) for the consolidated design system, interaction changes, React/Ant Design component mapping and production-only work.
