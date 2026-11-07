# THE BIG FASHION — Web entry update

- Existing storefront pages, product rendering, Supabase URL/key, checkout RPC, order RPCs, and account-scoped order behavior are retained.
- Browser entry on the home page now shows a bottom sheet with Download APK and Continue in Web.
- Continue in Web closes the sheet and leaves the storefront available without immediate login.
- Exactly 10 seconds after Continue in Web, a login overlay opens.
- Orders, tracking, and account pages still require authentication; checkout retains its existing authentication check.
- APK URL is intentionally left blank in `js/supabase-config.js` as `window.BF_APK_DOWNLOAD_URL`; replace it with the final HTTPS APK URL when supplied.
- Installed PWA/standalone mode skips the web-only entry chooser.
- The 10-second timer starts after the user taps Continue in Web.


## Vercel deployment (important)
- Deploy the CONTENTS of this folder as the project root. `index.html` must be at the root of the deployed output, not inside an extra `Customer_App/` folder.
- For a static HTML deployment, set Framework Preset to Other and Build Command to empty; Output Directory should be `.`.
- `vercel.json` is included for clean URLs and to prevent stale HTML/JS/CSS and service-worker caching during updates.
- The APK button remains a placeholder until `window.BF_APK_DOWNLOAD_URL` in `js/supabase-config.js` is set to the real APK URL.
