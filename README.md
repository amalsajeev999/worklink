# WorkLink (Next.js)

## Run locally
    npm install
    npm run dev

## Application flow
The application form starts blank, accepts editable contact details, a resume, a cover letter, and work experience, and saves the submitted demo application in the current browser session. This frontend prototype has no employer-submission backend, so applications and email confirmations are not sent.

## Microsoft Clarity
1. Create a project at https://clarity.microsoft.com and copy the Project ID.
2. Locally: copy `.env.example` to `.env.local` and paste the ID after `NEXT_PUBLIC_CLARITY_ID=`.
3. On Vercel: Project Settings > Environment Variables > add `NEXT_PUBLIC_CLARITY_ID`, then redeploy.

Every click on a button or link sends a Clarity custom event named `click: <label>`
(for example `click: Apply Now`). See counts in Clarity under Filters > Custom events.
Heatmaps also show total clicks per element.

## Browser smoke tests
Install Playwright's Chromium browser once, then run the end-to-end smoke suite:
    npx playwright install chromium
    npm run test:e2e

The suite covers navigation, sign in and account creation, job search and applications,
profile editing, company filters, resource tabs, newsletter feedback, footer destinations,
and Clarity click events.

## Deploy
Import the repository on Vercel. The Next.js preset is detected automatically.
