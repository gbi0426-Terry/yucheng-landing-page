# YU CHENG Landing Page

Static landing page for advertising traffic.

## Files

- `index.html`: page markup and GTM install
- `styles.css`: responsive layout and visual style
- `script.js`: slider, form validation, event tracking, CRM/Supabase hook placeholder
- `assets/`: client-provided images

## Tracking

GTM is installed with container ID:

```txt
GTM-PTVVPS9D
```

GA4 is configured through GTM with Measurement ID:

```txt
G-V4SV6SMRRH
```

Meta Pixel is configured through GTM with Pixel ID:

```txt
3983576251949201
```

Tracked events pushed to `dataLayer`:

- `cta_click`
- `line_click`
- `lead_form_submit`
- `lead_form_validation_error`

Tracking IDs are listed in `index.html`; GA4 and Meta Pixel fire from GTM:

```js
window.yuchengTrackingConfig = {
  gtmId: "GTM-PTVVPS9D",
  ga4MeasurementId: "G-V4SV6SMRRH",
  metaPixelId: "3983576251949201"
};
```

## CRM / Supabase Hook

The form currently validates on the frontend and stores a preview payload in `localStorage`.

Replace `submitLead(payload)` in `script.js` after the CRM or Supabase destination is confirmed.

Recommended production flow:

1. POST the payload to a server endpoint or Supabase Edge Function.
2. Validate and sanitize fields server-side.
3. Write to Supabase or forward to CRM.
4. Return success only after the write completes.

## Deployment

This project can be deployed as plain static files on GitHub Pages, Vercel, Netlify, or any static hosting service.
