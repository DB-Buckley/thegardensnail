# Garden Snail

React + TypeScript single-page site for Garden Snail in Hermanus.

## Run locally

Run `npm install`, then `npm run dev`. Create a production bundle with `npm run build`.

## Netlify Forms deployment checklist

1. In Netlify, use build command `npm run build` and publish directory `dist`.
2. Deploy the site, then open **Forms** in the Netlify dashboard. Confirm that `garden-snail-contact` appears; `dist/__forms.html` is the static declaration Netlify detects during the build.
3. Confirm the detected form lists the `bot-field` honeypot. Enable Netlify's Akismet spam filtering in the Forms settings if it is not already enabled.
4. Configure email notifications in **Forms → Form notifications** for `garden-snail-contact`.
5. Submit one genuine enquiry on the deployed site and verify it appears in Forms. Review both the verified submissions and spam views; honeypot-triggered and Akismet-flagged submissions may appear in Spam.

The browser sends a URL-encoded same-origin POST only after local validation succeeds. It includes the Netlify form name and honeypot value, and shows success only for an HTTP success response. Browser safeguards include a honeypot, input limits, repeated-content and excessive-link checks, payload limiting, and a short retry cooldown. These controls are not server-side security. If abuse increases, evaluate Netlify-supported reCAPTCHA or a server-side validation endpoint before adding either one.

## Content updates

Replace testimonial placeholders in `src/data/testimonials.ts`. Image mapping lives in `src/config/assets.ts`.
